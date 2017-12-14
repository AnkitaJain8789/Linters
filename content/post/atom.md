---
title: "Atom"
date: 2017-12-06T17:16:35+05:30
---

Atom is a text editor that's modern, approachable, yet hackable to the core—a tool you can customize to do anything but also use productively without ever touching a config file.

Steps to set-up a complete linting configuration in ATOM:

•	The prerequisite to any linting setup is to ensure that we have an ESLint installed.
To do so open command prompt and run:<br/>
npm install eslint --save-dev (Locally)<br/>
            			OR<br/>
npm i -g eslint (Globally)

•	If this local installation of ESLint is not found, Atom will use the built-in ESLint in the linter-eslint package itself.

•	The recent versions of ESLint do not use any rules by-default. This means we have to specify a configuration file for our project!

•	To specify the linting rules an eslintrc.* file should be created. This can be done in two ways:

*Manually: A simple JavaScript/JSON file can be created to specify configuration information for an enitre directry. This can be in the form of .eslintrc file or an eslintConfog field in package.json file.

*Using command Prompt: This will use initializer from eslint. We have to give the following command:<br/>
    eslint --init

•	This will prompt us to answer certain questions about the how we want to configure eslint and gives us option to set it up according to a popular style guide or by inspecting our JS. 

•	Once our eslintrc.* file is ready, we need a plugin to apply this smoothly in our code-base.
•	To download the plugin in ATOM we need to open settings view and Click on ‘Install’.

•	Search for ‘linter-eslint’ and install the package.

•	A detailed document of this plugin can be found on :
https://atom.io/packages/linter-eslint








