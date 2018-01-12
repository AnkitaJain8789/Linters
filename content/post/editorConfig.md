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

#### __Editor Config for Sublime Text__ -

•	Open Sublime Text.

•	Install __editorConfig__ with __Package Control__ and restart Sublime Text.

{{%
  video class="align-video" mp4="/media/sublime_editorConfig.mp4"
%}}

•	Restart the application(Sublime Text). To confirm that EditorConfig is installed correctly on your Sublime Text instance, click on _Preferences_ → _Package Settings_, now you should be able to see _EditorConfig_.

#### Supported Properties:

<ul>
	<li>indent_style</li>
	<li>indent_size</li>
	<li>tab_width</li>
	<li>end_of_line</li>
	<li>insert_final_newline</li>
	<li>trim_trailing_whitespace</li>
	<li>charset</li>
</ul>

#### Editing __editorConfig__ file:

{{%
  video class="align-video" mp4="/media/sublime_editorConfigWrite.mp4"
%}}


#### __Editor Config for VS Code__ -

1. Search and install <em>EditorConfig for VS Code</em> from the extensions.

2. Reload the editor

3. Add an .editorconfig file at the root of your project, its settings apply to all applicable files at that level and below. To override EditorConfig settings for a particular folder in the project such that it uses different conventions than the top-level EditorConfig file, just add an .editorconfig file to the folder. 

If root=true property is set, then VSCode doesn't look any further up the directory structure to search for any property if not found in .editorconfig file.

{{% figure src="/images/EditorConfig_Setup.gif" width="60%" alt="EditorConfig Setup in VSCode" %}}

##### Creating EditorConfig file:
{{% figure src="/images/EditorConfig_File.gif" width="60%" alt="Creating .editorconfig file" %}}

##### References:

http://editorconfig.org/
