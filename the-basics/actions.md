# ⚙️ Actions

* [Introduction](actions.md#introduction)
* [AsObject](actions.md#introduction-1)
* [As Controller](actions.md#introduction-2)

### [Introduction](actions.md#introduction) <a href="#introduction" id="introduction"></a>

**Classes that take care of one specific task.**

This package introduces a new way of organizing the logic of your Maginium applications by focusing on the actions your applications provide.

Instead of creating controllers, jobs, listeners, and so on, it allows you to create a PHP class that handles a specific task and run that class as anything you want.

### [AsObject](actions.md#introduction-1) <a href="#introduction" id="introduction"></a>

#### [#](https://www.laravelactions.com/2.x/as-object.html#make)`make` <a href="#make" id="make"></a>

Resolves the action from the container.

```
MyAction::make();

// Equivalent to:
app(MyAction::class);
```

#### [#](https://www.laravelactions.com/2.x/as-object.html#run)`run` <a href="#run" id="run"></a>

Resolves and executes the action.

```
MyAction::run($someArguments);

// Equivalent to:
MyAction::make()->handle($someArguments);
```

#### [#](https://www.laravelactions.com/2.x/as-object.html#runif)`runIf` <a href="#runif" id="runif"></a>

Resolves and executes the action if the condition is met.

```
MyAction::runIf(true, $someArguments);
```

#### [#](https://www.laravelactions.com/2.x/as-object.html#rununless)`runUnless` <a href="#rununless" id="rununless"></a>

Resolves and executes the action if some condition is not met.

```
MyAction::runUnless(false, $someArguments);
```

### [AsController](actions.md#introduction-2) <a href="#introduction" id="introduction"></a>

#### [#](https://www.laravelactions.com/2.x/as-controller.html#invoke)`__invoke` <a href="#invoke" id="invoke"></a>

Executes the action by delegating immediately to the `handle` method.

```
$action($someArguments);

// Equivalent to:
$action->handle($someArguments);
```

Whilst this method is not used, it has to be defined on the action to register the action as an invokable controller. When missing, Maginium will throw an exception warning us that we're trying to register a class as an invokable controller without the `__invoke` method. The truth is, the controller will be an instance of `ControllerDecorator` but the framework doesn't know that yet.

```
protected static function makeInvokable($action)
{
    if (! method_exists($action, '__invoke')) {
        throw new UnexpectedValueException("Invalid controller action: [{$action}].");
    }

    return $action.'@__invoke';
}
```

If you need to use the `__invoke` method for something else, you may [override it (opens a new window)](https://stackoverflow.com/a/11939306/11440277) with anything you want. The only requirement is that a `__invoke` method has to exist.

```
class MyAction
{
    use AsAction {
        __invoke as protected invokeFromMaginiumActions;
    }

    public function __invoke()
    {
        // ...
    }
}
```

### [#](https://www.laravelactions.com/2.x/as-controller.html#methods-used)Methods used <a href="#methods-used" id="methods-used"></a>

_Lists all methods recognized and used by the `ControllerDecorator`_

#### [#](https://www.laravelactions.com/2.x/as-controller.html#ascontroller)`asController` <a href="#ascontroller" id="ascontroller"></a>

It is called when used as an invokable controller. Uses the `handle` method directly when no `asController` method exists.

```
public function asController(User $user, Request $request): Response
{
    $article = $this->handle(
        $user,
        $request->get('title'),
        $request->get('body')
    );

    return redirect()->route('articles.show', [$article]);
}
```

#### [#](https://www.laravelactions.com/2.x/as-controller.html#jsonresponse)`jsonResponse` <a href="#jsonresponse" id="jsonresponse"></a>

Called after the `asController` method when the request expects JSON. The first argument is the return value of the `asController` method and the second argument is the request itself.

```
public function jsonResponse(Article $article, Request $request): ArticleResource
{
    return new ArticleResource($article);
}
```

#### [#](https://www.laravelactions.com/2.x/as-controller.html#htmlresponse)`htmlResponse` <a href="#htmlresponse" id="htmlresponse"></a>

Called after the `asController` method when the request expects HTML. The first argument is the return value of the `asController` method and the second argument is the request itself.

```
public function htmlResponse(Article $article, Request $request): Response
{
    return redirect()->route('articles.show', [$article]);
}
```

#### [#](https://www.laravelactions.com/2.x/as-controller.html#getcontrollermiddleware)`getControllerMiddleware` <a href="#getcontrollermiddleware" id="getcontrollermiddleware"></a>

Adds controller middleware directly in the action.

```
public function getControllerMiddleware(): array
{
    return ['auth', MyCustomMiddleware::class];
}
```

#### [#](https://www.laravelactions.com/2.x/as-controller.html#prepareforvalidation)`prepareForValidation` <a href="#prepareforvalidation" id="prepareforvalidation"></a>

Called right before authorization and validation is resolved.

```
public function prepareForValidation(ActionRequest $request): void
{
    $request->merge(['some' => 'additional data']);
}
```

#### [#](https://www.laravelactions.com/2.x/as-controller.html#authorize)`authorize` <a href="#authorize" id="authorize"></a>

Defines authorization logic for the controller.

```
public function authorize(ActionRequest $request): bool
{
    return $request->user()->role === 'author';
}
```

You may also return gate responses instead of booleans.

```
use Illuminate\Auth\Access\Response;

public function authorize(ActionRequest $request): Response
{
    if ($request->user()->role !== 'author') {
        return Response::deny('You must be an author to create a new article.');
    }

    return Response::allow();
}
```

#### [#](https://www.laravelactions.com/2.x/as-controller.html#rules)`rules` <a href="#rules" id="rules"></a>

Provides the validation rules for the controller.

```
public function rules(): array
{
    return [
        'title' => ['required', 'min:8'],
        'body' => ['required', IsValidMarkdown::class],
    ];
}
```

#### [#](https://www.laravelactions.com/2.x/as-controller.html#withvalidator)`withValidator` <a href="#withvalidator" id="withvalidator"></a>

Adds custom validation logic to the existing validator.

```
use Illuminate\Validation\Validator;

public function withValidator(Validator $validator, ActionRequest $request): void
{
    $validator->after(function (Validator $validator) use ($request) {
        if (! Hash::check($request->get('current_password'), $request->user()->password)) {
            $validator->errors()->add('current_password', 'Wrong password.');
        }
    });
}
```

#### [#](https://www.laravelactions.com/2.x/as-controller.html#aftervalidator)`afterValidator` <a href="#aftervalidator" id="aftervalidator"></a>

Adds an `after` callback to the existing validator. The example below is equivalent to the example provided in the `withValidator` method.

```
use Illuminate\Validation\Validator;

public function afterValidator(Validator $validator, ActionRequest $request): void
{
    if (! Hash::check($request->get('current_password'), $request->user()->password)) {
        $validator->errors()->add('current_password', 'Wrong password.');
    }
}
```

#### [#](https://www.laravelactions.com/2.x/as-controller.html#getvalidator)`getValidator` <a href="#getvalidator" id="getvalidator"></a>

DefineDefines your validator instead of the default one generated using `rules`, `withValidator`, etc.

```
use Illuminate\Validation\Factory;
use Illuminate\Validation\Validator;

public function getValidator(Factory $factory, ActionRequest $request): Validator
{
    return $factory->make($request->only('title', 'body'), [
        'title' => ['required', 'min:8'],
        'body' => ['required', IsValidMarkdown::class],
    ]);
}
```

#### [#](https://www.laravelactions.com/2.x/as-controller.html#getvalidationdata)`getValidationData` <a href="#getvalidationdata" id="getvalidationdata"></a>

Defines the data that should be used for validation. Defaults to: `$request->all()`.

```
public function getValidationData(ActionRequest $request): array
{
    return $request->all();
}
```

#### [#](https://www.laravelactions.com/2.x/as-controller.html#getvalidationmessages)`getValidationMessages` <a href="#getvalidationmessages" id="getvalidationmessages"></a>

Customize the messages of your validation rules.

```
public function getValidationMessages(): array
{
    return [
        'title.required' => 'Looks like you forgot the title.',
        'body.required' => 'Is that really all you have to say?',
    ];
}
```

#### [#](https://www.laravelactions.com/2.x/as-controller.html#getvalidationattributes)`getValidationAttributes` <a href="#getvalidationattributes" id="getvalidationattributes"></a>

Provides some human-friendly mapping to your request attributes.

```
public function getValidationAttributes(): array
{
    return [
        'title' => 'headline',
        'body' => 'content',
    ];
}
```

#### [#](https://www.laravelactions.com/2.x/as-controller.html#getvalidationredirect)`getValidationRedirect` <a href="#getvalidationredirect" id="getvalidationredirect"></a>

Customises the redirect URL when validation fails. Defaults to redirecting back to the previous page.

```
public function getValidationRedirect(UrlGenerator $url): string
{
    return $url->to('/my-custom-redirect-url');
}
```

#### [#](https://www.laravelactions.com/2.x/as-controller.html#getvalidationerrorbag)`getValidationErrorBag` <a href="#getvalidationerrorbag" id="getvalidationerrorbag"></a>

Customises the validator's error bag when validation fails. Defaults to: `default`.

```
public function getValidationErrorBag(): string
{
    return 'my_custom_error_bag';
}
```

#### [#](https://www.laravelactions.com/2.x/as-controller.html#getvalidationfailure)`getValidationFailure` <a href="#getvalidationfailure" id="getvalidationfailure"></a>

Overrides the validation failure altogether. Defaults to: `ValidationException`.

```
public function getValidationFailure(): void
{
    throw new MyCustomValidationException();
}
```

#### [#](https://www.laravelactions.com/2.x/as-controller.html#getauthorizationfailure)`getAuthorizationFailure` <a href="#getauthorizationfailure" id="getauthorizationfailure"></a>

Overrides the authorization failure. Defaults to: `AuthorizationException`.

```
public function getAuthorizationFailure(): void
{
    throw new MyCustomAuthorizationException();
}
```
