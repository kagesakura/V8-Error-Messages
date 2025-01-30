# V8 Error Messages
There are only V8 Error Messages that caught my attention. (not all errors)  

## SyntaxError: Private fields can not be deleted
\[Firefox] SyntaxError: private fields can't be deleted
```js
class A {
  a() {
    delete this.#a;
  }
}
```

## SyntaxError: Class constructor may not be a private method
\[Firefox] SyntaxError: a class constructor definition must be a plain public method
```js
class A {
  #constructor() {}
}
```

## SyntaxError: Unexpected private field
\[Firefox] SyntaxError: invalid access of private field on 'super'
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
\[Firefox] TypeError: already executing generator
```js
const generator = function*() {
  generator.next();
}();

generator.next();
```

## SyntaxError: Too many parameters in function definition (only 65534 allowed)
[SourceCode (too large)](syntaxerror_too_many_parameters_in_function_definition_only_65534_allowed.js)

## TypeError: The .size property is NaN
\[Firefox] TypeError: size is NaN
```js
new Set().union({ size: NaN })
```

## RangeError: '-1' is an invalid size
\[Firefox] RangeError: Set size must be non-negative
```js
new Set().union({ size: -1 })
```
