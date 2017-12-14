---
title: "ESLint Configuration"
date: 2017-12-06T17:16:35+05:30
---

ESLint supports numerous rules to manage a good code quality. But none of it is enabled by default.<br/>
There are certain rules that we recommend, should be included mandatorily. We have categorized them for a better understanding.

Possible Errors<br/>
These rules relate to possible syntax or logic errors in JavaScript code:<br/>
•	no-compare-neg-zero<br/>
The rule should warn against code that tries to compare against -0, since that will not work as intended. That is, code like x === -0 will pass for both +0 and -0.

•	no-cond-assign<br/>
In conditional statements, it is very easy to mistype a comparison operator (such as ==) as an assignment operator (such as =).

•	no-console<br/>
JavaScript is designed to execute in the browser, it’s considered a best practice to avoid using console statements. Such messages are considered to be present for debugging purposes and therefore not suitable to push to repository.
It is advisable to use a custom console, if required for logging the error messages.

•	no-constant-condition<br/>
A constant expression (for example, a literal) as a test condition might be a typo or development trigger for a specific behavior.<br/>
Example: <br/>
	if (false) {}, 0 ? a : b

•	no-debugger<br/>
The ’debugger’ statement is used to stop execution of JavaScript and start up a debugger at the current point in the code. This is not a good practice as now all the browsers are well equipped with debugging and development tools. Production code should definitely not contain debugger.

•	no-dupe-keys<br/>
Multiple properties with the same key in object literals can cause unexpected behavior in your application.<br/>
Example: <br/>
	Var foo = {
bar: “abcd”,
bar: “abcd”
}

•	no-duplicate-case<br/>
This rule disallows duplicate test expressions in case clause of Switch statements.If a switch statement has duplicate case clauses, it is likely that a programmer copied a case clause but forgot to change the test expression.

•	no-empty<br/>
Empty block statements, while not technically errors, usually occur due to refactoring that wasn’t completed. They can cause confusion when reading code.
This rule disallows empty block statements. This rule ignores block statements which contain a comment (for example, in an empty catch or finally block of try statement to indicate that execution should continue regardless of errors).

•	no-empty-character-class<br/>
Empty character classes in regular expressions do not match anything, they might be typing mistakes. This rule disallows empty character classes in regular expressions.
Example: var foo = /^abc[]/

•	no-ex-assign<br/>
If a catch clause in a try statement accidentally/purposely assigns another value to the exception parameter, it impossible to refer to this new error from that point on. This kind of assignment is absolutely destructive.

•	no-extra-semi : This rule disallows unnecessary semicolons which can showup due to typing mistakes.<br/>
Example: Var x = 5;;

•	no-func-assign : <br/>
This rule disallows reassigning function declarations. Overwriting/Reassigning a function written as a Function Declaration is often indicative of a mistake or issue.

•	no-inner-declarations: <br/>
This rule requires that function declarations (and, optionally, variable declarations) to be in the root of a program or the body of a function. A function declaration is only allowed in the first level of a program or the body of another function, though parsers sometimes erroneously accept them else where This only applies to function declarations

•	no-invalid-regexp: <br/>
This rule disallows invalid regular expression strings in RegExp constructors. For example, RegExp(‘[’) is not allowed. 

•	no-irregular-whitespace:<br/> 
This rule is aimed at catching invalid whitespace that is not a normal tab and space. Some of these characters may cause issues in modern browsers and others will be a debugging issue to spot.

•	no-obj-calls: <br/>
This rule disallows calling the Math, JSON and Reflect objects as functions. This rule was introduced in ESLint 0.0.9.

•	no-regex-spaces:<br/> 
This rule disallows multiple spaces in regular expression literals. 
Example: RegExp(“foo  bar”) is invalid.

•	no-sparse-arrays: <br/>
This rule disallows sparse array literals which have “holes” where commas are not preceded by elements. It does not apply to a trailing comma following the last element.<br/>
Example: var colours = [“blue”,, “red”]; is invalid<br/>
	      var colours = [“blue”, “red”, ]; is valid.<br/>

•	no-unexpected-multiline:<br/>
 This rule disallows confusing multiline expressions where a newline looks like it is ending a statement, but is not. The following example illustrates multiline expression.
Example: <br/>
Var foo = bar<br/>
(1 || 2).baz();

•	no-unreachable:<br/>
 This rule disallows unreachable code after return, throw, continue, and break statements. The function ‘foo()’ has unreachable code. <br/>
Function foo() {<br/>
	Return true;<br/>
	Console.log(“done”); }

•	no-unsafe-finally:<br/>
 This rule disallows return, throw, break, and continue statements inside finally blocks. It allows indirect usages, such as in function or classdefinitions.

•	no-unsafe-negation:<br/>
 This rule disallows negating the left operand of Relational Operators. Relational Operators are: in operator, instanceof operator.

•	use-isnan: <br/>
This rule disallows comparisons to ‘NaN’. NaN is a special value of the Number type. It’s used to represent any of the “not-a-number” values represented by the double-precision 64-bit format as specified by the IEEE Standard for Binary Floating-Point Arithmetic.

•	valid-typeof:<br/>
 This rule enforces comparing typeof expressions to valid string literals. Mostly the result of the typeof operator is would be one of the following string literals: “undefined”, “object”, “boolean”, “number”, “string”, “function” and “symbol”. 
Best Practices

•	no-case-declarations<br/>
This rule disallows lexical declarations (let, const, function and class) in case/default clauses. The reason is that the lexical declaration is visible in the entire switch block but it only gets initialized when it is assigned, which will only happen if the case where it is defined is reached.
This rule aims to prevent access to uninitialized lexical bindings as well as accessing hoisted functions across case clauses.

•	no-empty-pattern<br/>
This rule aims to flag any empty patterns in destructured objects and arrays, and as such, will report a problem whenever one is encountered.<br/>
Example:  var {} = foo; - INCORRECT<br/>
var {A = {} } = foo; - CORRECT<br/>

•	no-fallthrough<br/>
The switch statement in JavaScript is one of the more error-prone constructs of the language thanks in part to the ability to “fall through” from one case to the next. This rule is aimed at eliminating unintentional fall through of one case to the other. As such, it flags any fall through scenarios that are not marked by a comment.

•	no-global-assign<br/>
JavaScript environments contain a number of built-in global variables, such as window in browsers and process in node.js. In almost all cases, you do not want to assign a value to these global variables as doing so could result in losing access to important functionality. For example, you probably do not want to do this in browser code:
Window = { };<br/>
This rule disallows modifications to read-only global variables.

•	no-octal<br/>
Octal literals are numerals that begin with a leading zero, such as:
var num = 071;  // 57
Because the leading zero which identifies an octal literal has been a source of confusion and error in JavaScript code, ECMAScript 5 deprecates the use of octal numeric literals. The rule disallows octal literals.

•	no-redeclare<br/>
In JavaScript, it is possible to redeclare the same variable name using var. This can lead to confusion as to where the variable is actually declared and initialized. This rule is aimed at eliminating variables that have multiple declarations in the same scope.

•	no-self-assign<br/>
Self-assignments have no effect, so probably those are an error due to incomplete refactoring. Those indicate that what you should do is still remaining. Example:  foo = foo;
This rule is aimed at eliminating self-assignments.

•	no-unused-labels<br/>
Labels that are declared and not used anywhere in the code are most likely an error due to incomplete refactoring. This rule is aimed at eliminating unused labels. If you do not want to be notified about unused labels, then it’s safe to disable this rule.

•	no-useless-escape<br/>
Escaping non-special characters in strings, template literals, and regular expressions does not have any effect, as demonstrated in the following example: let foo = “hol\a”;  // foo = “hola”;
This rule flags escapes that can be safely removed without changing behavior. Example – “\’” (incorrect) , “\”” (correct)
Variables

•	no-delete-var<br/>
The purpose of the delete operator is to remove a property from an object. Using the delete operator on a variable might lead to unexpected behavior.
This rule disallows the use of the delete   operator on variables. If ESLint parses code in strict mode, the parser (instead of this rule) reports the error.<br/>
Example: var x; delete x;   - INCORRECT

•	no-undef<br/>
This rule can help you locate potential Reference Errors resulting from misspellings of variable and parameter names, or accidental implicit globals (for example, from forgetting the var keyword in a for loop initializer)
Any reference to an undeclared variable causes a warning, unless the variable is explicitly mentioned in a  /*global …*/ comment.

•	no-unused-vars<br/>
Variables that are declared and not used anywhere in the code are most likely an error due to incomplete refactoring. Such variables take up space in the code and can lead to confusion by readers
This rule is aimed at eliminating unused variables, functions, and parameters of functions.

