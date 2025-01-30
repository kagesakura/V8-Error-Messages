> as of Jan 31 2025

# V8 Error Messages
There are only V8 Error Messages that caught my attention. (not all errors)  

## SyntaxError: Private fields can not be deleted
\[Firefox] SyntaxError: private fields can't be deleted  
\[Safari on iOS] SyntaxError: Cannot delete private field #a.
```js
class A {
  a() {
    delete this.#a;
  }
}
```

## SyntaxError: Class constructor may not be a private method
\[Firefox] SyntaxError: a class constructor definition must be a plain public method  
\[Safari on iOS] SyntaxError: Cannot declare a private method named '#constructor'.
```js
class A {
  #constructor() {}
}
```

## SyntaxError: Unexpected private field
\[Firefox] SyntaxError: invalid access of private field on 'super'  
\[Safari on iOS] SyntaxError: Unexpected private name #a. Cannot access private names from super.
```js
class A {
  a() {
    super.#a;
  }
}
```

## SyntaxError: Cannot use new with import
\[Firefox] SyntaxError: unexpected token: '('  
\[Safari on iOS] SyntaxError: Cannot use new with import.
```js
new import("");
```

## TypeError: Generator is already running
\[Firefox] TypeError: already executing generator  
\[Safari on iOS] TypeError: Generator is executing
```js
const generator = function*() {
  generator.next();
}();

generator.next();
```

## SyntaxError: Too many parameters in function definition (only 65534 allowed)
This is an error unique to V8 Engine, I think.  
[SourceCode (too large)](syntaxerror_too_many_parameters_in_function_definition_only_65534_allowed.js)

## TypeError: The .size property is NaN
\[Firefox] TypeError: size is NaN  
\[Safari on iOS] TypeError: Set.prototype.union expects other.size to be a non-NaN number
```js
new Set().union({ size: NaN })
```

## RangeError: '-1' is an invalid size
\[Firefox] RangeError: Set size must be non-negative  
\[Safari on iOS] (The thrown error is not RangeError but TypeError 🤯!! I don't think this behavior conforms to the specification)
```js
new Set().union({ size: -1 })
```
