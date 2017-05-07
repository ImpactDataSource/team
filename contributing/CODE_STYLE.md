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
be linted with ESLint.

##### General Rules:
* No space at top of file.
* One space at end of file.
* Never 2 lines between content.
* Always single space after comma.
* Never spaces inside parentheses.

##### Objects:
* Space inside brackets when on same line.
  * `{ foo: bar, fizz: bazz }`
  * `const { computed, run } = Ember;`
* No extra whitespace when object spans multiple lines.


##### Functions:
* No space after word function or function name.
* Single space between parentheses and curly bracket.
* No white space after curly bracket.

* Anonymous functions:

```
columns.forEach(function(column) {
  controller.send('save', column.get('columnName'), column.get('cellValues'));
});

```

* Named functions:

```
ASQ(function _findDistrict(done) {
  TaxDistrict.model.findById(req.params.id).exec(done.errfcb);
});
```

* Arrow functions:

```
Ember.run(() => {
  this.updateRawValue();
});
```

##### Indentation:
* Use increments of 2 spaces for indentation.

##### If statements:
* No inline if statements.
  * ie. `if (this === that) { return something };`
  * exception: ternary operators:
    * ie. `value = array[i] !== undefined ? array[i] : "0";`
* Space between curly brackets and `else`/`else if`
* `else`/`else if` on same line as previous closing bracket.

```
if (something === somethingElse) {
  return statement;
}  else if {
  return statement;
} else {
  return statement;
}
```
