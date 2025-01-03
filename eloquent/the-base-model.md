# The Base Model

## Magento-Elasticsearch Base Model Integration

This document outlines a structured and technical approach to creating a base model for seamless Elasticsearch integration within a Magento framework. The base model serves as a foundational class, enabling scalable, efficient, and maintainable interactions with Elasticsearch.

***

### **1. Define the Base Model**

The base model encapsulates core Elasticsearch functionalities while remaining extensible for specific use cases.

```php
namespace Vendor\Module\Model;

use Elasticsearch\ClientBuilder;

class ElasticsearchBase
{
    protected $indexName;
    protected $client;

    public function __construct()
    {
        $this->client = ClientBuilder::create()->build();
        $this->indexName = 'default_index'; // Placeholder, override in child classes
    }
}
```

This ensures every derived class can inherit core Elasticsearch client functionalities.

***

### **2. Configurable Index and Type**

Allow derived classes to specify custom index names and types, offering flexibility for varied use cases.

```php
protected $indexName = 'magento_index';
protected $type = 'document_type';
```

***

### **3. CRUD Operations**

#### **Indexing Data**

Efficiently index Magento entities in Elasticsearch:

```php
public function indexDocument($id, $data)
{
    $params = [
        'index' => $this->indexName,
        'id' => $id,
        'body' => $data
    ];
    return $this->client->index($params);
}
```

#### **Retrieve Document**

Fetch documents by ID for quick access:

```php
public function getDocument($id)
{
    $params = [
        'index' => $this->indexName,
        'id' => $id
    ];
    return $this->client->get($params);
}
```

***

### **4. Traits for Reusability**

Enhance the modularity and maintainability of the base model by utilizing reusable traits.

#### **Timestamp Handling**

```php
trait ElasticsearchTimestamps
{
    public function getCurrentTimestamp()
    {
        return date('Y-m-d H:i:s');
    }
}
```

Traits can be used across multiple models to standardize functionality.

***

### **5. Casts and Mutators**

Handle Magento-specific data structures with precision by implementing casting methods.

```php
protected function castData(array $data)
{
    return [
        'price' => (float)$data['price'],
        'stock' => (int)$data['stock'],
    ];
}
```

This ensures data consistency during indexing and retrieval.

***

### **6. Bulk Operations**

Enable efficient handling of large datasets using bulk operations:

```php
public function bulkIndex(array $documents)
{
    $params = ['body' => []];

    foreach ($documents as $id => $data) {
        $params['body'][] = [
            'index' => [
                '_index' => $this->indexName,
                '_id' => $id
            ]
        ];
        $params['body'][] = $data;
    }

    return $this->client->bulk($params);
}
```

Bulk indexing minimizes the overhead of multiple HTTP requests to Elasticsearch.

***

### **7. Metadata and Debugging**

Log Elasticsearch responses to facilitate debugging and transparency.

```php
public function logQueryResponse($response)
{
    \Magento\Framework\App\ObjectManager::getInstance()
        ->get(\Psr\Log\LoggerInterface::class)
        ->info(json_encode($response));
}
```

This method provides insight into Elasticsearch operations for debugging.

***

### **8. Extending for Specific Models**

Derived classes such as `ProductElasticsearch` can override properties and methods to cater to specific business needs:

```php
class ProductElasticsearch extends ElasticsearchBase
{
    protected $indexName = 'products';
    protected $type = 'product';

    public function formatProductData($product)
    {
        return [
            'name' => $product->getName(),
            'price' => $product->getPrice(),
        ];
    }
}
```

This approach ensures that Elasticsearch operations are tailored to specific Magento entity requirements.

***

### **Conclusion**

The Magento-Elasticsearch Base Model establishes a robust and flexible foundation for interacting with Elasticsearch. By centralizing common functionalities and providing extensibility for specific use cases, this architecture supports scalable and maintainable development within the Magento ecosystem. Use this structure as a starting point to customize and enhance Elasticsearch capabilities tailored to your business requirements.
