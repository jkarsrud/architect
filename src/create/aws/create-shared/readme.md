# Automagical `src/shared` directory

The contents of `src/shared` get copied into every function at `node_modules/@architect/shared` whenever you run:

- `npx sandbox`
- `npx hydrate`
- `npx deploy`

This means the modules in this folder can be required from any function in your Architect project.

For example, `src/shared/layout.js` can be required like so:

```javascript
var layout = require('@architect/shared/layout')
```


## Organizing `src/shared`

Organize shared code however it makes sense for your project.

Here are some ideas:

- `src/shared/middleware`
- `src/shared/helpers`
- `src/shared/lib`

Also, feel free to overwrite the contents of this file to describe your project's shared code structure for your teammates.


## Use caution!

Everything in `src/shared` will be copied into all of your project's Lambdas, which has the potential to quickly bloat your application.

Remember you want to keep your Lambda functions sub-5MB for optimal coldstart performance.