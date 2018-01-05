---
title: "Editor Config"
date: 2017-12-06T17:16:35+05:30
---

__EditorConfig__ helps developers define and maintain consistent coding styles between different editors and IDEs. The EditorConfig project consists of a file format for defining coding styles and a collection of text editor plugins that enable editors to read the file format and adhere to defined styles. EditorConfig files are easily readable and they work nicely with version control systems.


Example file
Below is an example .editorconfig file setting end-of-line and indentation styles for Python and JavaScript files.

```javascript
// EditorConfig helps developers define and maintain consistent
// coding styles between different editors and IDEs
// editorconfig.org
root = true


[*]
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
indent_style = space
indent_size = 2

// Typescript and JavaScript files
[*.{ts,js]
indent_style = space
indent_size = 2

// Handlebar template files
[*.hbs]
insert_final_newline = false
indent_style = space
indent_size = 2

// CSS and SASS files
[*.{css,scss}]
indent_style = space
indent_size = 2

// HTML files
[*.html]
indent_style = space
indent_size = 2

// Diff and Markdown files
[*.{diff,md}]
trim_trailing_whitespace = false
```
#### __Editor Config for Atom__ -

1. Install required Editor Config package
#####    __i. apm install editorconfig via command prompt__
#####    __ii. Preferences → Settings → Install → Search for editorconfig → install__

2. Open a project containing an .editorconfig file.
3. Whenever you open a file in the project (or change any .editorconfig file from within Atom), EditorConfig evaluates the EditorConfig settings for the current file.
4. EditorConfig then applies these settings to your current editor pane. Any change you make from now on will follow the EditorConfig settings. __EditorConfig won't automatically fix older files that it considers to be malformed.__
5. You can always check your EditorConfig settings against the current file using the __EditorConfig: Show State command__. You can try to fix malformed files using the command __EditorConfig: Fix File__
