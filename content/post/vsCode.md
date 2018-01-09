---
title: "Vscode_config"
date: 2017-12-06T17:09:30+05:30

---

Visual Studio Code is a source code editor developed by Microsoft for Windows, Linux and macOS. It includes support for debugging, embedded Git control, syntax highlighting, intelligent code completion, snippets, and code refactoring. It is also customizable, so users can change the editor's theme, keyboard shortcuts, and preferences. It is free and open-source,although the official download is under a proprietary license.

Visual Studio Code is based on Electron, a framework which is used to deploy Node.js applications for the desktop running on the Blink layout engine. Although it uses the Electron framework,the software does not use Atom and instead employs the same editor component (codenamed "Monaco") used in Visual Studio Team Services (formerly called Visual Studio Online).


### ES Lint<br/>


Linting is a type of static analysis that is frequently used to find problematic patterns or code that doesn’t adhere to certain style guidelines.Linting tools like __ESLint__ allow developers to discover problems with their JavaScript code without executing it.

#### Steps to set-up a complete __ESLINT__ configuration in __VSCODE__:

•	The prerequisite to any linting setup is to ensure that we have an _ESLint installed_.<br/>

#####  1. __Node.js (>=4.x)__
#####  2. __npm version 2+__

•	Go to command Prompt and run the command:<br/>
#####   __npm install eslint --save-dev (LOCALLY)__
#####   __npm i -g eslint (GLOBALLY)__
   
•	Install a plugin for Eslint that could read .eslintrc.json file.

•	.eslintrc.json  configuration file is the one that will be used to override the         exisitng rule of eslint.

•	To install plugin open VSCode -> Extensions(Ctrl + Shift + X) -> Install the            plugin named as - ESLint .

•	Prior to checking for any linting error make sure  Eslint  Plugin  is successfully installed.

##### Demo for ESLint setup: 

{{%
  video class="align-video" mp4="/media/esLint_installation.mp4"
%}}

##### References:

https://eslint.org/docs/user-guide/configuring