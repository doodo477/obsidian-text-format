# Text Format

[![Obsidian Downloads](https://img.shields.io/badge/dynamic/json?color=7e6ad6&labelColor=34208c&label=Obsidian%20Downloads&query=$['obsidian-text-format'].downloads&url=https://raw.githubusercontent.com/obsidianmd/obsidian-releases/master/community-plugin-stats.json&)](obsidian://show-plugin?id=obsidian-text-format) ![GitHub stars](https://img.shields.io/github/stars/Benature/obsidian-text-format?style=flat)

Sometimes I encounter some issues like  
1. I copy some text from pdf or some other source, but the copied content is out of format. For example, there are more than one space between words or one paragraph brokes into several lines.  
2. I want to lowercase the letters when they are all uppercase, etc.

Therefore, I wrote this plugin to format selected text lowercase/uppercase/capitalize/titlecase or remove redundant spaces/newline characters, and other features listed below.

[Install this plugin right now.] (obsidian://show-plugin?id=obsidian-text-format)
## Features

Press <kbd>cmd/ctrl+P</kbd> to enter the command. 👇

Or you can consider to bind custom hotkeys to those commands.

### Basic

| Command                                                         | Description                                                                                                        |
| --------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| **Lowercase** selected text                                     | Lowercase all letters in selection                                                                                 |
| **Uppercase** selected text                                     | Uppercase all letters in selection                                                                                 |
| **Capitalize** all **words** in selected text                   | Capitalize all words in selection                                                                                  |
| **Capitalize** only first word of **sentence** in selected text | Capitalize only first word of sentence(s) in selection                                                             |
| **Title case** selected text                                    | Capitalize words but leave certain words in lower case in selection *(Note: not support Cyrillic strings for now)* |


### List
| Command                 | Description                                                                                                                                      |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| Format **bullet** list  | Change `•` into bullet list, i.e. `- `; split every bullet point into single line; and remove blank lines.                                       |
| Format **ordered** list | Change `*)`(star could be any letter) into ordered list (e.g. `1. `, `2. `); split every ordered point into single line; and remove blank lines. |

### PDF copy / OCR

| Command                                    | Description                                                                                                                                                                                                                                        |
| ------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Remove redundant **spaces** in selection   | Ensure only one space between words                                                                                                                                                                                                                |
| Remove **blank line(s)**                   | replace `\n\n` with `\n`                                                                                                                                                                                                                           |
| Merge **broken paragraph(s)** in selection | Change selected lines into single-line, except lines are separated by blank line(s). *At the same time, blank lines will be merged into one blank line(optional, default enable), and redundant spaces will be removed(optional, default enable).* |
| Remove **hyphens**                         | Remove hyphens (like when pasting text from pdf) [#15](https://github.com/Benature/obsidian-text-format/issues/15)                                                                                                                                 |
| **Split** line(s) by **blanks**            | Replace ` ` with `\n` for OCR use case.                                                                                                                                                                                                            |
| Convert to **Chinese character** (,;:!?)   | For OCR use case.                                                                                                                                                                                                                                  |


### Others
| Command                                     | Description                                                                  |
| ------------------------------------------- | ---------------------------------------------------------------------------- |
| Decode **URL**                              | Decode URL for better reading and shorter url.                               |
| Convert single letter into **math** mode    | e.g. convert `P` into `$P$` (latex), apply for all single letter except `a`. |
| Convert **Mathpix** array to markdown table | Convert latex array generated by Mathpix to markdown table format            |


## Some Example


- lowercase
  ```diff
  - Hello, I am using Obsidian.
  + hello, i am using obsidian.
  ```
- uppercase
  ```diff
  - Hello, I am using Obsidian.
  + HELLO, I AM USING OBSIDIAN.
  ```
- capitalize word
  ```diff
  - Hello, I am using Obsidian.
  + Hello, I Am Using Obsidian.
  ```
- capitalize sentence
  ```diff
  - hello, I am using Obsidian.
  + Hello, I am using Obsidian.
    ^
  ```
- title case
  ```diff
  - Obsidian is a good app.
  + Obsidian Is a Good App.
                ^
  ```
- redundant spaces
  ```diff
  - There  are so   many redundant      blanks
  + There are so many redundant blanks
  ```
- merge broken paragraph
  ```diff
  - This paragraph is broken 
  - into several lines. I want 
  - those lines merged!
  - 
  - And this is second paragraph. There is a blank line between 
  - two paragraph, indicating that they should not be merged into 
  - one paragraph!

  + This paragraph is broken into several lines. I want those lines merged!
  +
  + And this is second paragraph. There is a blank line between two paragraph, indicating that they should not be merged into one paragraph!
  ```
- bullet list
  ```diff
  - • first, blahblah • second, blahblah • third, blahblah
  
  + - first, blahblah 
  + - second, blahblah 
  + - third, blahblah
  ```
- ordered list
  ```diff
  - a) first, blahblah b) second, blahblah c) third, blahblah
  - i) first, blahblah ii) second, blahblah iii) third, blahblah
  
  + 1. first, blahblah 
  + 2. second, blahblah 
  + 3. third, blahblah
  ```
![demo](https://user-images.githubusercontent.com/35028647/121776728-149ea500-cbc1-11eb-89ee-f4afcb0816ed.gif)
