---
title: "Vscode_config"
date: 2017-12-06T17:09:30+05:30

---

Visual Studio Code is a source code editor developed by Microsoft for Windows, Linux and macOS. It includes support for debugging, embedded Git control, syntax highlighting, intelligent code completion, snippets, and code refactoring. It is also customizable, so users can change the editor's theme, keyboard shortcuts, and preferences. It is free and open-source,although the official download is under a proprietary license.

Visual Studio Code is based on Electron, a framework which is used to deploy Node.js applications for the desktop running on the Blink layout engine. Although it uses the Electron framework,the software does not use Atom and instead employs the same editor component (codenamed "Monaco") used in Visual Studio Team Services (formerly called Visual Studio Online).

<strong>EditorConfig: </strong> It helps you to maintain consistent coding styles and settings in a codebase, regardless of the editor or IDE you use.

<strong>Setup: </strong>

1. Search and install <em>EditorConfig for VS Code</em> from the extensions.

2. Reload the editor

3. Add an .editorconfig file at the root of your project, its settings apply to all applicable files at that level and below. To override EditorConfig settings for a particular folder in the project such that it uses different conventions than the top-level EditorConfig file, just add an .editorconfig file to the folder. 

If root=true property is set, then VSCode doesn't look any further up the directory structure to search for any property if not found in .editorconfig file.

<strong>Supported Properties :</strong>
<ul>
	<li>indent_style</li>
	<li>indent_size</li>
	<li>tab_width</li>
	<li>end_of_line</li>
	<li>insert_final_newline</li>
	<li>trim_trailing_whitespace</li>
	<li>charset</li>
</ul>

<strong>References :</strong>

http://editorconfig.org/



ES Lint:

•	linting is a type of static analysis that is frequently used to find problematic patterns or code that doesn’t adhere to certain style guidelines.

•	Linting tools like ESLint allow developers to discover problems with their JavaScript code without executing it.

	Prerequisite For Linting For Any Code  Base:

•	Node.js (>=4.x), npm version 2+.
•	Go to command Prompt and run the command:
    npm install eslint --save-dev (Locally)

            	OR

•	npm i -g eslint (Globally)

•	Install a plugin for Eslint that could read .eslintrc.json file.

•	.eslintrc.json  configuration file is the one that will be used to override the         exisitng rule of eslint.
•	To install plugin open VSCode -> Extensions(Ctrl + Shift + X) -> Install the            plugin named as - ESLint .

•	Prior to checking for any linting error make sure your PC/ Laptop has Eslint            Plugin and eslint is successfully installed.

•	To check for errors open any existing script file or you can make once -> bottom        left click on "x" a workspace will open up with four tabs.

•	click on 'PROBLEMS' there all linting errors like: quote, white spaace, double          declared errors could be seen along with the count of number of erros.


EXAMPLE FOR REFERENCE:
  <h5>• eslint no-new-object</h5>

var myObject = new Object(); -INCORRECT

var myObject = {}; - CORRECT

<h5>• comma-dangle</h5>

var foo = {bar: "baz",qux: "quux",} -INCORRECT

 var foo = {bar: 'baz',qux: 'quux'};  -CORRECT


 <h5>• no-array-constructor</h5>

new Array(0, 1, 2) -INCORRECT

Array(500)  -CORRECT