---
title: "Atom Configuration"
date: 2017-12-06T17:16:35+05:30
---

__Atom__ is a text editor that's modern, approachable, yet hackable to the core — a tool you can customize to do anything but also use productively without ever touching a config file.

#### Steps to set-up a complete __LINTING__ configuration in __ATOM__:

•	The prerequisite to any linting setup is to ensure that we have an _ESLint installed_.<br/>

#####  1. __Node.js (>=4.x)__
#####  2. __npm version 2+__

•	Go to command Prompt and run the command:<br/>
##### __npm install eslint --save-dev (LOCALLY)__
##### __npm i -g eslint (GLOBALLY)__

<!-- {{% asciinema id="153243" speed="1" size="small" theme="monokai" cols="80" rows="20" loop="1" %}} -->
<script src="https://asciinema.org/a/153243.js" id="asciicast-153243" async></script>

•	If this local installation of ESLint is __NOT__ found, Atom will use the built-in ESLint in the linter-eslint package itself.

•	The recent versions of ESLint do not use any rules by-default. This means we have to specify a configuration file for our project.

•	To specify the linting rules an eslintrc.* file should be created. This can be done in two ways:

##### 1. Manually:
A simple JavaScript/JSON file can be created to specify configuration information for an entire directory. This can be in the form of .eslintrc file or an eslintConfig field in package.json file. A detailed document to create .eslintrc file can be found here:

##### https://eslint.org/docs/user-guide/configuring

{{%
  video class="align-video" mp4="/media/atom_local_eslintrc.mp4"
%}}

##### 2. Using command Prompt:
This will use initializer from eslint. We have to give the following command:<br/>

#####  __eslint --init__

This will prompt us to answer certain questions about the how we want to configure eslint and gives us option to set it up according to a popular style guide or by inspecting our JS.

<!-- {{% asciinema id="153254" speed="1" size="small" theme="monokai" cols="80" rows="20" loop="1" %}} -->
<script src="https://asciinema.org/a/153254.js" id="asciicast-153254" async></script>


•	Once our eslintrc.* file is ready, we need a plugin to apply this smoothly in our code-base.

•	To download the plugin in ATOM we need to open settings view and Click on ‘Install’.

•	Search for packages - __"linter-eslint"__ and __"linter"__ and install the packages.

•	A detailed document of this plugin can be found on :
##### https://atom.io/packages/linter-eslint
##### https://atom.io/packages/linter

{{%
  video mp4="/media/atom_package_installation.mp4"
%}}

#### Sample Example:

{{% figure class="align-left" src="/images/atom_input.png" width="60%" alt="JavaScript Code and associated .eslintrc.js file" %}}

#### How to execute ?

<!-- {{% asciinema id="153259" speed="1" size="small" theme="monokai" cols="80" rows="20" loop="1" %}} -->
<script src="https://asciinema.org/a/153259.js" id="asciicast-153259" async></script>

#### Output:

{{% figure class="align-left" src="/images/atom_output.png" width="60%" alt="JavaScript Code and associated .eslintrc.js file" %}}
