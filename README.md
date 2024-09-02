# rat (routers are terrible)
rat is a client-side router which makes it easy to map javascript functions to URL pathnames.

## Installation
If rat becomes popular, I will host it on a CDN for fast delivery. Until then, copy the source code [directly](https://raw.githubusercontent.com/Phillip-England/rat/main/index.js).

```html
<head>
    <script src='/path/to/rat.js'></script>
</head>
```

## The `rat` Object
In the bottom of `rat.js`, a rat object is declared

```js
const rat = new Rat()
```

This makes the rat object *immediately* available when you include `rat.js` in your project.

You don't have to instatiate rat yourself, we got you.

function helloMiddleware(next) {
    return () => {
        console.log('Hello, Before Middleware!')
        next()
        console.log('Hello, After Middleware!')
    }
}

rat.use("*", helloMiddleware)

rat.at("/", () => {
    console.log('/')
})
