<!-- background: #184bc6 -->
<!-- color: #fff -->

***
# JavaScript Linters

***

Syntax validation to eliminate suspicious code and violations of code style.

***
# Suspicious code (bugs potentially)

Undefined variables

```js
    function bad() {
        return foo;
    }
```

***
# Suspicious code (bugs potentially)

Lack of brackets

```js
if (someVal)
    someVal += otherVal;
    someVal++;
    return someVal;    
```

*** 
# Code Style

Invalid

```js
function BAD_func (b , c){ 
      var a = 3333
    return a;
  }
```

Valid

```js
function goodFunc(b, c) { 
    var a = 3333;
    return a;
}
```

***
# [JSLint]

- &copy; Douglas Crockford, 2002
- too strong rules, enforcing "The Good Parts"

****
# [JSHint]

- &copy; Anton Kovalyov, 2010
- more configurable
- support ES6

****
# How to use 

- CLI application `jshint file.js`
- config file `.jshintrc`, JSON with comments

***
# .jshintrc

- rules
- environments (browser, node, etc.)
- globals

```json
{
    "bitwise"       : true,
    "camelcase"     : true, 

    "node": true,

    "globals": {
        "foo": true,
        "bar": false // readonly
    }
}
```

***
# Configuration per file

```
/*globals foo: false, baz: false */
/*jshint camelcase: false */

// ....

/* jshint ignore:start */
// ...
/* jshint ignore:end */
```

***
# Output

- list of errors 
- line and position of error, description
- different formats (human readable, JSON, XML, etc.)

```
demo.js: line 2, col 14, 'main' is defined but never used.
demo.js: line 2, col 19, 'b' is defined but never used.
```

***
# Favorite rules

add picture Crockford + bootstrap

- `undef` Require all non-global variables to be declared (prevents global leaks)
- `unused` Require all defined variables be used

***
# `asi` Require semicolons

***
- `curly` Require {} for every new block or scope
- `newcap` Require capitalization of all constructor functions e.g. `new F()`
- `indent` Spaces to indent
- `camelcase` 
- `quotmark`

***

# Below the trunk

- tokenize

JSHint 3.0 promise more modular, own rules, ...

***

# Enter Esprima

***

# ESLint

- working with AST 
- more sofisticated rules
- each rule in separate file
- can write own rules
- 99% rules of JSHint
- two level of invalidation -- warning and error

***

# Same configuration 

- `.eslintrc` (JSON or YAML)
- `/*eslint */` 

***

# Favorite rules

- `no-dupe-keys`
- `no-floating-decimal`
- `block-scoped-vars`
- `consistent-this` "consistent-this": [2, "self"],
- `func-style`
- `radix`
- `semi` can enforce absent of semi
- convert !!!!

****

# Drawbacks

- still in-dev
- does not support ES6+ (will be 0.5.0)
- a bit slow (5x JSHint)

****

# JSCS

- JavaScript Code Style checker
- based on Esprima
- rules can be appied to any keyword

****

# Integration (when CLI is not enough)

****

# Editors

****

# Sublime Text

- SublimeLinter
- screenshot

****

# ...and all other editors

****

# Deploy process

- before/after testing
- gulp, grunt, ...

****

# Favorite rules

- `requireCurlyBraces`
- `requireSpaceAfterKeywords`
- `validateLineBreaks`
- `validateJSDoc`

****

# Computer, fix my code

****

# EditorConfig

- simple format
- plugins for almost all IDE
- claims to become a standard

****

# Favorite options

```
root = true

[*]
indent_style = space
indent_size = 4
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true

[*.{md,jade}]
trim_trailing_whitespace = false
```

****

# JavaScript Formatters

****

# JS Beautifier

- based on tokens
- stable, in general
- not very configurated :(

****

# Favorite rules

- "indent_size": <%= opts.indentSize %>,
- "indent_char": " ",
- "preserve_newlines": true,
- "max_preserve_newlines": 2,
- "brace_style": "collapse",
- "keep_array_indentation": false,
- "keep_function_indentation": false,
- "space_before_conditional": true,
- "space_in_paren": false,

****

# ESFormatter

- based on Esprima
- seems configurated
- unstable :(

****

# Rules

try animation

****

# Integration

****

# Editors

****

# Sublime Text

* JsFormat JS Beautifier
* EsFormatter for ESFormatter

****

# Integration

- same as linter
- better diff than replace

****

# Plan to follow

****

# 1. Install EditorConfig

****

# 2. Install your favorite linters and add them to your favorite editor

****

# 3. Try to lint your existing code

****

# 4. Play with settings

****

# 5. Try to install and configure formatters

****

```
$ npm install generator-linters -g
```

****
# Thank you!

[JSLint]: http://jslint.com/  "JSLint"
[JSHint]: http://jshint.org/  "JSHint"
