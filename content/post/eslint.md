---
title: "ESLint Configuration"
date: 2017-12-06T17:16:35+05:30
---

ESLint supports numerous rules to manage a good code quality. But none of it is enabled by default.<br/>
There are certain rules that we recommend, should be included mandatorily. We have categorized them for a better understanding.

### Possible Errors<br/>
These rules relate to possible syntax or logic errors in JavaScript code:<br/>

##### •	no-compare-neg-zero<br/>
The rule should warn against code that tries to compare against -0, since that will not work as intended. That is, code like x === -0 will pass for both +0 and -0.
Examples of __incorrect__ code for this rule:
```javascript
if (x === -0) {
    // doSomething()...
}
```
Examples of __correct__ code for this rule:
```javascript
// case 1:
if (x === 0) {
    // doSomething()...
}
// case 2:
if (Object.is(x, -0)) {
    // doSomething()...
}
```

##### •	no-cond-assign<br/>
In conditional statements, it is very easy to mistype a comparison operator (such as ==) as an assignment operator (such as =).
Examples of __incorrect__ code for this rule:
```javascript
// Unintentional assignment
var x;
if (x = 0) {
    var b = 1;
}
```
Examples of __correct__ code for this rule:
```javascript
// Assignment replaced by comparison
var x;
if (x === 0) {
    var b = 1;
}
```

##### •	no-console<br/>
JavaScript is designed to execute in the browser, it’s considered a best practice to avoid using console statements. Such messages are considered to be present for debugging purposes and therefore not suitable to push to repository.
It is advisable to use a __custom console__, if required for logging the error messages.
Examples of __incorrect__ code for this rule:
```javascript
console.log("Log a debug level message.");
console.warn("Log a warn level message.");
console.error("Log an error level message.");
```
Examples of __correct__ code for this rule:
```javascript
// custom console
Console.log("Hello world!");
```

##### •	no-constant-condition<br/>
A constant expression (for example, a literal) as a test condition might be a typo or development trigger for a specific behavior.<br/>
Example: <br/>
```javascript
  // Example 1 :
	if (false) {
		// doSomething()...
	}
  // Example 2 :
	0 ? a : b;
```

##### •	no-debugger<br/>
The ’debugger’ statement is used to stop execution of JavaScript and start up a debugger at the current point in the code. This is not a good practice as now all the browsers are well equipped with debugging and development tools. Production code should definitely not contain debugger.
Examples of __incorrect__ code for this rule:
```javascript
function isTruthy(x) {
    debugger;
    return Boolean(x);
}
```
Examples of __correct__ code for this rule:
```javascript
function isTruthy(x) {
    return Boolean(x);
}
```

##### •	no-dupe-keys<br/>
Multiple properties with the same key in object literals can cause unexpected behavior in your application.<br/>
Example: <br/>
```javascript
var foo = {
    bar: "baz",
    bar: "qux"
};

var foo = {
    "bar": "baz",
    bar: "qux"
};

var foo = {
    0x1: "baz",
    1: "qux"
};
```

##### •	no-duplicate-case<br/>
This rule disallows duplicate test expressions in case clause of Switch statements.If a switch statement has duplicate case clauses, it is likely that a programmer copied a case clause but forgot to change the test expression.
Examples of __incorrect__ code for this rule:

```javascript
/*eslint no-duplicate-case: "error"*/

var a = 1;

switch (a) {
    case 1:
        break;
    case 2:
        break;
    case 1:         // duplicate test expression
        break;
    default:
        break;
}
```
##### •	no-empty<br/>
Empty block statements, while not technically errors, usually occur due to refactoring that wasn’t completed. They can cause confusion when reading code.
This rule disallows empty block statements. This rule ignores block statements which contain a comment (for example, in an empty catch or finally block of try statement to indicate that execution should continue regardless of errors).
Examples of __incorrect__ code for this rule:
```javascript

if (foo) {
}

while (foo) {
}

switch(foo) {
}

try {
    doSomething();
} catch(ex) {

} finally {

}
```
Examples of __correct__ code for this rule:
```javascript
if (foo) {
    // empty
}

while (foo) {
    /* empty */
}

try {
    doSomething();
} catch (ex) {
    // continue regardless of error
}

try {
    doSomething();
} finally {
    /* continue regardless of error */
}
```

##### •	no-empty-character-class<br/>
Empty character classes in regular expressions do not match anything, they might be typing mistakes. This rule disallows empty character classes in regular expressions.
Example:
```javascript
var foo = /^abc[]/;
```

##### •	no-ex-assign<br/>
If a catch clause in a try statement accidentally/purposely assigns another value to the exception parameter, it impossible to refer to this new error from that point on. This kind of assignment is absolutely destructive.
Examples of __incorrect__ code for this rule:
```javascript
try {
    // code
} catch (e) {
    e = 10;
}
```
Examples of __correct__ code for this rule:
```javascript
try {
    // code
} catch (e) {
    var foo = 10;
}
```

##### •	no-extra-semi : This rule disallows unnecessary semicolons which can showup due to typing mistakes.<br/>
Example:
```javascript
var foo = 5;;
```

##### •	no-func-assign : <br/>
This rule disallows reassigning function declarations. Overwriting/Reassigning a function written as a Function Declaration is often indicative of a mistake or issue.
Examples of __incorrect__ code for this rule:
```javascript
function foo() {}
foo = bar;

function foo() {
    foo = bar;
}
```
Examples of __correct__ code for this rule:
```javascript
var foo = function () {}
foo = bar;

function foo(foo) { // `foo` is shadowed.
    foo = bar;
}

function foo() {
    var foo = bar;  // `foo` is shadowed.
}
```

##### •	no-inner-declarations: <br/>
This rule requires that function declarations (and, optionally, variable declarations) to be in the root of a program or the body of a function. A function declaration is only allowed in the first level of a program or the body of another function, though parsers sometimes erroneously accept them else where This only applies to function declarations
```javascript
// Good
function doSomething() { }

// Bad
if (test) {
    function doSomethingElse () { }
}

function anotherThing() {
    var fn;

    if (test) {

        // Good
        fn = function expression() { };

        // Bad
        function declaration() { }
    }
}
```

##### •	no-invalid-regexp: <br/>
This rule disallows invalid regular expression strings in RegExp constructors. For example, RegExp(‘[’) is not allowed.
Examples of __incorrect__ code for this rule:
```javascript
RegExp('[')

RegExp('.', 'z')

new RegExp('\\')
```
Examples of __correct__ code for this rule:
```javascript
RegExp('.')

new RegExp

this.RegExp('[')
```

##### •	no-irregular-whitespace:<br/>
This rule is aimed at catching invalid whitespace that is not a normal tab and space. Some of these characters may cause issues in modern browsers and others will be a debugging issue to spot.

##### •	no-obj-calls: <br/>
This rule disallows calling the Math, JSON and Reflect objects as functions. This rule was introduced in ESLint 0.0.9.
Examples of __incorrect__ code for this rule:
```javascript
var math = Math();
var json = JSON();
var reflect = Reflect();
```
Examples of __correct__ code for this rule:
```javascript
function area(r) {
    return Math.PI * r * r;
}
var object = JSON.parse("{}");
var value = Reflect.get({ x: 1, y: 2 }, "x");
```

##### •	no-regex-spaces:<br/>
This rule disallows multiple spaces in regular expression literals.
Examples of __incorrect__ code for this rule:
```javascript
var re = /foo   bar/;
var re = new RegExp("foo   bar"); //In this regular expression, it’s very hard to tell how many spaces are intended to be matched
```
Examples of __correct__ code for this rule:
```javascript
var re = /foo {3}bar/;
var re = new RegExp("foo {3}bar");
```

##### •	no-sparse-arrays: <br/>
This rule disallows sparse array literals which have “holes” where commas are not preceded by elements. It does not apply to a trailing comma following the last element.<br/>

Examples of __incorrect__ code for this rule:
```javascript
var colours = [“blue”,, “red”];
```
Examples of __correct__ code for this rule:
```javascript
var colours = [“blue”, “red”];
```

##### •	no-unexpected-multiline:<br/>
 This rule disallows confusing multiline expressions where a newline looks like it is ending a statement, but is not. The following example illustrates multiline expression.
Example: <br/>
```javascript
var foo = bar
(1 || 2).baz();
```

##### •	no-unreachable:<br/>
 This rule disallows unreachable code after return, throw, continue, and break statements. The function ‘foo()’ has unreachable code.
 Example: <br/>
 ```javascript
function foo() {
	return true;
	console.log('done');
}
 ```

##### •	no-unsafe-finally:<br/>
 This rule disallows return, throw, break, and continue statements inside finally blocks. It allows indirect usages, such as in function or classdefinitions.
 Examples of __incorrect__ code for this rule:
 ```javascript
 let foo = function() {
    try {
        return 1;
    } catch(err) {
        return 2;
    } finally {
        return 3;
    }
};
 ```
 Examples of __correct__ code for this rule:
 ```javascript
 let foo = function() {
     try {
         return 1;
     } catch(err) {
         return 2;
     } finally {
         console.log("hola!");
     }
 };
 ```

##### •	no-unsafe-negation:<br/>
 This rule disallows negating the left operand of Relational Operators. Relational Operators are: in operator, instanceof operator.
 Examples of __incorrect__ code for this rule:
 ```javascript
 if (!key in object) {
    // operator precedence makes it equivalent to (!key) in object
    // and type conversion makes it equivalent to (key ? "false" : "true") in object
}

if (!obj instanceof Ctor) {
    // operator precedence makes it equivalent to (!obj) instanceof Ctor
    // and it equivalent to always false since boolean values are not objects.
}
 ```
 Examples of __correct__ code for this rule:
 ```javascript
 if (!(key in object)) {
    // key is not in object
}

if (!(obj instanceof Ctor)) {
    // obj is not an instance of Ctor
}

if(("" + !key) in object) {
    // make operator precedence and type conversion explicit
    // in a rare situation when that is the intended meaning
}
 ```

##### •	use-isnan: <br/>
This rule disallows comparisons to ‘NaN’. NaN is a special value of the Number type. It’s used to represent any of the “not-a-number” values represented by the double-precision 64-bit format as specified by the IEEE Standard for Binary Floating-Point Arithmetic.
Examples of __incorrect__ code for this rule:
```javascript

if (foo == NaN) {
    // ...
}

if (foo != NaN) {
    // ...
}
```
Examples of __correct__ code for this rule:
```javascript

if (isNaN(foo)) {
    // ...
}

if (!isNaN(foo)) {
    // ...
}
```

##### •	valid-typeof:<br/>
 This rule enforces comparing typeof expressions to valid string literals. Mostly the result of the typeof operator is would be one of the following string literals: “undefined”, “object”, “boolean”, “number”, “string”, “function” and “symbol”.
 Examples of __incorrect__ code for this rule:
 ```javascript
typeof foo === "strnig"
typeof foo == "undefimed"
typeof bar != "nunber"
typeof bar !== "function"
 ```
 Examples of __correct__ code for this rule:
 ```javascript
 typeof foo === "string"
 typeof bar == "undefined"
 typeof foo === baz
 typeof bar === typeof qux
 ```

##### •	no-case-declarations<br/>
This rule disallows lexical declarations (let, const, function and class) in case/default clauses. The reason is that the lexical declaration is visible in the entire switch block but it only gets initialized when it is assigned, which will only happen if the case where it is defined is reached.
This rule aims to prevent access to uninitialized lexical bindings as well as accessing hoisted functions across case clauses.
Examples of __incorrect__ code for this rule:
```javascript
switch (foo) {
    case 1:
        let x = 1;
        break;
    case 2:
        const y = 2;
        break;
    case 3:
        function f() {}
        break;
    default:
        class C {}
}
```
Examples of __correct__ code for this rule:
```javascript
// Declarations outside switch-statements are valid
const a = 0;

switch (foo) {
    // The following case clauses are wrapped into blocks using brackets
    case 1: {
        let x = 1;
        break;
    }
    case 2: {
        const y = 2;
        break;
    }
    case 3: {
        function f() {}
        break;
    }
    case 4:
        // Declarations using var without brackets are valid due to function-scope hoisting
        var z = 4;
        break;
    default: {
        class C {}
    }
}
```

##### •	no-empty-pattern<br/>
This rule aims to flag any empty patterns in destructured objects and arrays, and as such, will report a problem whenever one is encountered.<br/>
Examples of __incorrect__ code for this rule:
```javascript
var {} = foo;
var [] = foo;
var {a: {}} = foo;
var {a: []} = foo;
function foo({}) {}
function foo([]) {}
function foo({a: {}}) {}
function foo({a: []}) {}
```
Examples of __correct__ code for this rule:
```javascript
var {a = {}} = foo;
var {a = []} = foo;
function foo({a = {}}) {}
function foo({a = []}) {}
```

##### •	no-fallthrough<br/>
The switch statement in JavaScript is one of the more error-prone constructs of the language thanks in part to the ability to “fall through” from one case to the next. This rule is aimed at eliminating unintentional fall through of one case to the other. As such, it flags any fall through scenarios that are not marked by a comment.
Examples of __incorrect__ code for this rule:
```javascript
switch(foo) {
    case 1:
        doSomething();

    case 2:
        doSomething();
}
```
Examples of __correct__ code for this rule:
```javascript
switch(foo) {
    case 1:
        doSomething();
        break;

    case 2:
        doSomething();
}

function bar(foo) {
    switch(foo) {
        case 1:
            doSomething();
            return;

        case 2:
            doSomething();
    }
}

switch(foo) {
    case 1:
        doSomething();
        throw new Error("Boo!");

    case 2:
        doSomething();
}

switch(foo) {
    case 1:
    case 2:
        doSomething();
}

switch(foo) {
    case 1:
        doSomething();
        // falls through

    case 2:
        doSomething();
}
// Note that the last case statement in these examples does not cause a warning because there is nothing to fall through into.
```

##### •	no-global-assign<br/>
JavaScript environments contain a number of built-in global variables, such as window in browsers and process in node.js. In almost all cases, you do not want to assign a value to these global variables as doing so could result in losing access to important functionality. For example, you probably do not want to do this in browser code:
This rule disallows modifications to read-only global variables.
Examples of __incorrect__ code for this rule:
```javascript
// case 1:
Object = null
undefined = 1
// case 2: /*eslint-env browser*/
window = {}
length = 1
top = 1
// case 3: /*globals a:false*/
a = 1
```
Examples of __correct__ code for this rule:
```javascript
// case 1:
a = 1
var b = 1
b = 2
// case 2: /*eslint-env browser*/
onload = function() {}
// case 3: /*globals a:true*/
a = 1
```

##### •	no-octal<br/>
Octal literals are numerals that begin with a leading zero, such as:
var num = 071;  // 57
Because the leading zero which identifies an octal literal has been a source of confusion and error in JavaScript code, ECMAScript 5 deprecates the use of octal numeric literals. The rule disallows octal literals.
Examples of __incorrect__ code for this rule:
```javascript
var num = 071;
var result = 5 + 07;
```

##### •	no-redeclare<br/>
In JavaScript, it is possible to redeclare the same variable name using var. This can lead to confusion as to where the variable is actually declared and initialized. This rule is aimed at eliminating variables that have multiple declarations in the same scope.
Examples of __incorrect__ code for this rule:
```javascript
var a = 3;
var a = 10;
```
Examples of __correct__ code for this rule:
```javascript
var a = 3;
// ...
a = 10;
```

##### •	no-self-assign<br/>
Self-assignments have no effect, so probably those are an error due to incomplete refactoring. Those indicate that what you should do is still remaining. Example:  foo = foo;
This rule is aimed at eliminating self-assignments.
Examples of __incorrect__ code for this rule:
```javascript

foo = foo;

[a, b] = [a, b];

[a, ...b] = [x, ...b];

({a, b} = {a, x});
```
Examples of __correct__ code for this rule:
```javascript
foo = bar;
[a, b] = [b, a];

// This pattern is warned by the `no-use-before-define` rule.
let foo = foo;

// The default values have an effect.
[foo = 1] = [foo];
```

##### •	no-unused-labels<br/>
Labels that are declared and not used anywhere in the code are most likely an error due to incomplete refactoring. This rule is aimed at eliminating unused labels. If you do not want to be notified about unused labels, then it’s safe to disable this rule.
Examples of __incorrect__ code for this rule:
```javascript
A: var foo = 0;

B: {
    foo();
}

C:
for (let i = 0; i < 10; ++i) {
    foo();
}
```
```javascript
A: {
    if (foo()) {
        break A;
    }
    bar();
}

B:
for (let i = 0; i < 10; ++i) {
    if (foo()) {
        break B;
    }
    bar();
}
```

##### •	no-useless-escape<br/>
Escaping non-special characters in strings, template literals, and regular expressions does not have any effect, as demonstrated in the following example: let foo = “hol\a”;  // foo = “hola”;
This rule flags escapes that can be safely removed without changing behavior. Example – “ \' ” (incorrect) , “ \” ” (correct)
variables

##### •	no-delete-var<br/>
The purpose of the delete operator is to remove a property from an object. Using the delete operator on a variable might lead to unexpected behavior.
This rule disallows the use of the delete   operator on variables. If ESLint parses code in strict mode, the parser (instead of this rule) reports the error.<br/>
Example:
```javascript
var x;
delete x;   /* INCORRECT */
```

##### •	no-undef<br/>
This rule can help you locate potential Reference Errors resulting from misspellings of variable and parameter names, or accidental implicit globals (for example, from forgetting the var keyword in a for loop initializer)
Any reference to an undeclared variable causes a warning, unless the variable is explicitly mentioned in a  /* global*/ comment.
Examples of __incorrect__ code for this rule:
```javascript
var a = someFunction();
b = 10;
```
Examples of __correct__ code for this rule:
```javascript
/*global someFunction b:true*/
var a = someFunction();
b = 10;
```

##### •	no-unused-vars<br/>
variables that are declared and not used anywhere in the code are most likely an error due to incomplete refactoring. Such variables take up space in the code and can lead to confusion by readers
This rule is aimed at eliminating unused variables, functions, and parameters of functions.
