---
title: "Vscode_config"
date: 2017-12-06T17:09:30+05:30

---

Visual Studio Code is a source code editor developed by Microsoft for Windows, Linux and macOS. It includes support for debugging, embedded Git control, syntax highlighting, intelligent code completion, snippets, and code refactoring. It is also customizable, so users can change the editor's theme, keyboard shortcuts, and preferences. It is free and open-source,although the official download is under a proprietary license.

Visual Studio Code is based on Electron, a framework which is used to deploy Node.js applications for the desktop running on the Blink layout engine. Although it uses the Electron framework,the software does not use Atom and instead employs the same editor component (codenamed "Monaco") used in Visual Studio Team Services (formerly called Visual Studio Online).

### EditorConfig<br/>

It helps you to maintain consistent coding styles and settings in a codebase, regardless of the editor or IDE you use.

##### Setup:

1. Search and install <em>EditorConfig for VS Code</em> from the extensions.

2. Reload the editor

3. Add an .editorconfig file at the root of your project, its settings apply to all applicable files at that level and below. To override EditorConfig settings for a particular folder in the project such that it uses different conventions than the top-level EditorConfig file, just add an .editorconfig file to the folder. 

If root=true property is set, then VSCode doesn't look any further up the directory structure to search for any property if not found in .editorconfig file.

{{% figure src="/images/EditorConfig_Setup.gif" width="60%" alt="EditorConfig Setup in VSCode" %}}

##### Supported Properties:
<ul>
	<li>indent_style</li>
	<li>indent_size</li>
	<li>tab_width</li>
	<li>end_of_line</li>
	<li>insert_final_newline</li>
	<li>trim_trailing_whitespace</li>
	<li>charset</li>
</ul>

##### Creating EditorConfig file:
{{% figure src="/images/EditorConfig_File.gif" width="60%" alt="Creating .editorconfig file" %}}

##### References:

http://editorconfig.org/


### ES Lint<br/>

Linting is a type of static analysis that is frequently used to find problematic patterns or code that doesn’t adhere to certain style guidelines.Linting tools like ESLint allow developers to discover problems with their JavaScript code without executing it.

<strong>Set up: </strong>

1.	Node.js (>=4.x), npm version 2+.

2.	Go to command Prompt and run the command:
    npm install eslint --save-dev (Locally) / npm i -g eslint (Globally)
   
3.	Install a plugin for Eslint that could read .eslintrc.json file.

4.	.eslintrc.json  configuration file is the one that will be used to override the         exisitng rule of eslint.
5.	To install plugin open VSCode -> Extensions(Ctrl + Shift + X) -> Install the            plugin named as - ESLint .

6.	Prior to checking for any linting error make sure your PC/ Laptop has Eslint            Plugin and  is successfully installed.

<strong>Demo for ESLint setup: </strong>

http://recordit.co/XPvFo2R37c 

<strong>References :</strong>

https://eslint.org/docs/user-guide/configuring