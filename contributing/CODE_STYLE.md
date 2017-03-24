Code style
==

Projects can be manually linted with `npm run lint`. It is recommended to
configure your IDE with appropriate linting and not rely on the CI process to
catch code style issues.

#### JavaScript

All server-side Javascript should utilize any available ECMAScript 2015 (ES6)
features supported by Node that do not require a runtime flag. Unless otherwise
specified by the project, ~~all front-end Javascript is run through
[webpack](https://webpack.github.io/) and [Babel](https://babeljs.io/) which
transpiles to browser-compatible ES5.~~ Ember does a lot of this for us.

Code style follows a slightly relaxed Google Javascript style guide and should
be linted with ESLint. See the [.eslintrc.js file](./.eslintrc.js) in this
repository for the current list of exceptions configured.
