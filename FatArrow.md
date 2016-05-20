# Upgrade Node

```
brew update
brew install node
npm upgrade npm
```Create a playground

# Part 1

## Fat Arrows

What is `result` after running this code?

```js
let result = [1,2,3].map(n => n + 1)
```

```js
let a = [1,2,3], things = [];

a.forEach(function (b) {
  things.push(b)
})

a.forEach(b => things.push(b))
```

ES5 original rules of `this`:

- starts out as window
- when you call a function ​_on_​ an object, `this` is set to that object (`this` is evaluated when you ​_call_​ the function, not when you define it)
- you can "fix" the value of `this` by using `bind`
- you can set the value of `this` when calling a function using `apply` or `call`

"use strict":

- `this` starts out undefined

use fat arrows:

- `this` is lexically scoped

```js
var obj = {
  names: ["John Cena", "The Rock"],
  stuff: function() {
    console.log(this.names.length);
    [1,2,3].forEach(n => {
      [3].forEach(y => {
        console.log(n, y, arguments, this)
      })
    })
  }
}rg

obj.stuff("x", "y", "z")
```

```js
var obj = {
  names: ["John Cena", "The Rock"],
  stuff: () => {
    [1,2,3].forEach(function(n) {
      [3].forEach(function(y) {
        console.log(n, y, arguments, self)
      })
    })
  }
}
obj.stuff("x", "y", "z")
