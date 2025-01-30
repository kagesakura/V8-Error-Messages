# V8-ErrorMessages
Only V8 Errors that caught my attention

## SyntaxError: Private fields can not be deleted
```js
class A {
  a() {
    delete this.#a;
  }
}
```

## SyntaxError: Class constructor may not be a private method
```js
class A {
  #constructor() {}
}
```

## SyntaxError: Unexpected private field
```js
class A {
  a() {
    super.#a;
  }
}
```

## SyntaxError: Cannot use new with import
```js
new import("");
```

## TypeError: Generator is already running
```js
const generator = function*() {
  generator.next();
}();

generator.next();
```

## SyntaxError: Too many parameters in function definition (only 65534 allowed)
[SourceCode (too large)](syntaxerror_too_many_parameters_in_function_definition_only_65534_allowed.js)
