---
title: "Sublime_config"
date: 2017-12-06T17:09:17+05:30

---

Sublime Text is a proprietary cross-platform source code editor with a Python application programming interface (API). It natively supports many programming languages and markup languages, and functions can be added by users with plugins, typically community-built and maintained under free-software licenses.


#### __Process to install Sublime editorconfig:__
<p>Install Sublime Text editor software from https://www.sublimetext.com/3 (depending on the OS which you are using).</p>

Once Sublime Text editor is installed, we will have to install the sublime editorconfig by the steps given below:

•	The prerequisite to any linting setup is to ensure that we have an _ESLint installed_.<br/>

  1. __Node.js (>=4.x)__
  2. __npm version 2+__


•	Open the command prompt from the main folder. If your project doesnt have package.json, you can create one by running the command - __npm init__.

{{%
  video class="align-video" mp4="/media/sublime_packageJson.mp4"
%}}

•	In the Command prompt, give the command __npm install –g eslint__. After installation is done, run the command __eslint --init__, then set of questions will be asked in the command prompt. Select the answers accordingly. Once all the questions are answered a __.eslintrc.js__ file will be created in the specified folder.

{{%
  video class="align-video" mp4="/media/sublime_installation.mp4"
%}}

•	Detailed description can be found in https://www.npmjs.com/package/eslint and https://eslint.org/docs/user-guide/configuring

•	Do linting by running the command __eslint file_name.js__.

•	All the errors in your JS file will be shown here, based on the preferences(answers) selected while creating eslintrc.js file

{{%
  video class="align-video" mp4="/media/sublime_finderror.mp4"
%}} 

•	Potentially fixable errors can be fixed by running the command __eslint file_name.js --fix__

{{% figure class="align-left" src="/images/sublime_codefix.png" width="60%" alt="potential code fix" %}}