---
title: "Sublime_config"
date: 2017-12-06T17:09:17+05:30

---

Sublime Text is a proprietary cross-platform source code editor with a Python application programming interface (API). It natively supports many programming languages and markup languages, and functions can be added by users with plugins, typically community-built and maintained under free-software licenses.


<h3>Process to install Sublime editorconfig:</h4>
<p>Install Sublime Text editor software from https://www.sublimetext.com/3 (depending on the OS which you are using).</p>

Once Sublime Text editor is installed, we will have to install the sublime editorconfig by following the steps given below:

1.	Go the link - https://github.com/sindresorhus/editorconfig-sublime#readme.
2.	Click on “Clone or download” button.
3.	Once the file is downloaded, unzip the file. For example, my folder is C:\Users\aaldi\Downloads\sublime_config\editorconfig-sublime-master
4.	Once the file is unzipped, inside the same folder, create a folder with JS file. Ex: C:\Users\aaldi\Downloads\sublime_config\editorconfig-sublime-master\JS\Example.js
5.	In this JS file, write some code using the sublime editor and save it.
6.	Open the command prompt from the main folder (C:\Users\aaldi\Downloads\sublime_config\editorconfig-sublime-master).
7.	In the Command prompt, give the command – “npm install –g eslint”
8.	Installation will be started and set of steps will be executed.
9.	Once the execution is done, give the command – “eslint –init”
10.	Set of questions will be asked in the command prompt.
11.	Select the answers accordingly as shown above as per your requirements using arrow keys.
12.	Once all the questions are answered a “.eslintrc.js” file will be created in the specified folder. 
13.	Do linting using the command “eslint JS/Example.js”.
14.	All the errors in your JS file will be shown here, based on the preferences(answers) selected in step no.11 

