# locast

A cool ass localStorage proxy.

It basically gives you localStorage access like a normal object.

_I'm all about that syntactical sugar._

```js
import initLocast from 'locast'

const onGet = (target, property) => {
  console.log('getting from localStorage:', property)
}

const onSet = (target, property, value) => {
  console.log('setting in localStorage:', property, value)
}

const locast = initLocast(onGet, onSet)

locast.foo = 'FOO'
// setting in localStorage: foo "FOO"

locast.foo
// getting from localStorage: foo
```