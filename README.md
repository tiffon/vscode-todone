# ToDone

## This is very much a work in progress. 

Unfortunately, I've ran into an issue I've been unable to circumvent, so far:

> [How to customize the color of custom syntax tokens in VSCode extension](https://stackoverflow.com/questions/46377151/how-to-customize-the-color-of-custom-syntax-tokens-in-vscode-extension)

As a result, the only way I know of to apply the colors for the grammar are through user settings. So, if the extension is installed, user settings then need to be updated.

The good news is: That works. But, it's not exactly a smooth installation process, so I haven't published this extension.

## What it looks like

![](https://raw.github.com/tiffon/vscode-todone/master/example.png)

## How to install

- First, install the extension
  - Check out the repo
  - Go to the extensions panel in VSCode, then click the menu at the top right part of the panel, the ellipsis
  - Select "Install from VSIX"
  - Find the *.vsix file in the repo
- Next, update your user settings to color the todone grammar
  - Copy the following chunk into your user settings
    - Note: If you've already defined some settings in `editor.tokenColorCustomizations`, then the following should be appended, either in the root of the setting or in the `"textMateRules"` if you've already defined a few settings in there

```json
    "editor.tokenColorCustomizations": {
        "textMateRules": [
            {
                "scope": "entity.name.class.todone",
                "settings": {
                    "foreground": "#0088ff"
                }
            },
            {
                "scope": "symbol.definition.task-heading.todone",
                "settings": {
                    "foreground": "#ff8800"
                }
            }
            {
                "scope": [
                    "text.todone"
                ],
                "settings": {
                    "foreground": "#666"
                }
            },
            {
                "scope": [
                    "entity.name.class.todone"
                ],
                "settings": {
                    "foreground": "#66D9EF"
                }
            },
            {
                "scope": [
                    "punctuation.definition.class-block.todone"
                ],
                "settings": {
                    "foreground": "#505050"
                }
            },
            {
                "scope": [
                    "keyword.operator.completed.todone"
                ],
                "settings": {
                    "foreground": "#53e442"
                }
            },
            {
                "scope": [
                    "keyword.operator.completed.secondary.todone"
                ],
                "settings": {
                    "foreground": "#345d3d"
                }
            },
            {
                "scope": [
                    "storage.type.task.completed.todone .storage.task-note.todone"
                ],
                "settings": {
                    "foreground": "#444"
                }
            },
            {
                "scope": [
                    "keyword.operator.ignore.todone"
                ],
                "settings": {
                    "foreground": "#c06030"
                }
            },
            {
                "scope": [
                    "keyword.operator.ignore.secondary.todone"
                ],
                "settings": {
                    "foreground": "#c06030"
                }
            },
            {
                "scope": [
                    "keyword.operator.ignore.desc.todone"
                ],
                "settings": {
                    "foreground": "#904f31"
                }
            },
            {
                "scope": [
                    "keyword.operator.ignore.punctuation.desc.todone"
                ],
                "settings": {
                    "foreground": "#c06030"
                }
            },
            {
                "scope": [
                    "keyword.operator.ignore.secondary.todone"
                ],
                "settings": {
                    "foreground": "#c0603044"
                }
            },
            {
                "scope": [
                    "punctuation.definition.disaster.begin.todone"
                ],
                "settings": {
                    "foreground": "#fff"
                }
            },
            {
                "scope": [
                    "storage.type.task.completed.todone",
                    "storage.type.task.ignore.todone"
                ],
                "settings": {
                    "foreground": "#444"
                }
            },
            {
                "scope": [
                    "storage.task-note.em"
                ],
                "settings": {
                    "foreground": "#904f31"
                }
            },
            {
                "scope": [
                    "storage.task-note.em.comment.todone"
                ],
                "settings": {
                    "foreground": "#ccc"
                }
            },
            {
                "scope": [
                    "storage.task-note",
                    "storage.type.task"
                ],
                "settings": {
                    "foreground": "#565752"
                }
            },
            {
                "scope": [
                    "punctuation.definition.note"
                ],
                "settings": {
                    "foreground": "#505050"
                }
            },
            {
                "scope": [
                    "keyword.operator.task"
                ],
                "settings": {
                    "foreground": "#3a3a3a"
                }
            },
            {
                "scope": [
                    "keyword.operator.task.numeral"
                ],
                "settings": {
                    "foreground": "#3a3a3a"
                }
            },
            {
                "scope": [
                    "entity.name.task.lvl1.todone"
                ],
                "settings": {
                    "foreground": "#bbb"
                }
            },
            {
                "scope": [
                    "entity.name.task.lvl2.todone"
                ],
                "settings": {
                    "foreground": "#97c17a"
                }
            },
            {
                "scope": [
                    "entity.name.task.lvl3.todone"
                ],
                "settings": {
                    "foreground": "#ae81ff"
                }
            },
            {
                "scope": [
                    "entity.name.task.lvl4.todone"
                ],
                "settings": {
                    "foreground": "#ffeb3f"
                }
            },
            {
                "scope": [
                    "keyword.operator.task.lvl5.todone"
                ],
                "settings": {
                    "foreground": "#f92672"
                }
            },
            {
                "scope": [
                    "entity.name.task.lvl5.todone"
                ],
                "settings": {
                    "foreground": "#fff"
                }
            },
        ]
    }
```

Restart.

[The dishes are done, man](https://www.youtube.com/watch?v=wn8XFiAwLkM)

## About

This package is a simple tool for creating to do lists with the following features:

* Hierarchically organized tasks
* 5 levels of importance for tasks
* Notes of any length for any task
* Set a task to either _completed_ or _cancelled_
* Set a task to an _emergency state_

![](https://raw.github.com/tiffon/sublime-to-done/master/img/example.png)

To do lists are just plain text files with syntax highlighting applied. The intent is for this to make them easy to manage.

The language syntax is **ToDone**, and files with the extension `todo` are automatically set to the this language syntax.

## Content

### Tasks

The format for a task item is generally a hyphen then a hard-tab then the task title:

![](https://raw.github.com/tiffon/sublime-to-done/master/img/basic-task.png)

```
-       Some title
```

The number of hyphens indicates the importance of the task: 5 hyphens for the most important, 1 hyphen for the least important.

![](https://raw.github.com/tiffon/sublime-to-done/master/img/task-importance.png)

```
-       Not that important
-----   Very important
```

### Sub tasks

Sub tasks are the same as any other task, they are just indented.

![](https://raw.github.com/tiffon/sublime-to-done/master/img/sub-tasks.png)

```
-       A top level task
        -       First sub task
        -       Second sub task
```

### Notes

A task can have notes associated with it. There are three formats for notes:

**Same line** - All text after a colon `:`

![](https://raw.github.com/tiffon/sublime-to-done/master/img/note-same-line.png)

```
-       Some title: This is a note
```

**New line** - Lines of text with a greater indentation than the task's first hyphen

![](https://raw.github.com/tiffon/sublime-to-done/master/img/note-new-line.png)

```
-       Some title
        This is a note
```

**Note block** - Blocks of text starting and ending with three forward slashes `///`

![](https://raw.github.com/tiffon/sublime-to-done/master/img/note-block.png)

```
-       Some title ///
        This is a note
        - this is still the note
        - and so is this
        ///
```

Text within a note can be emphasized by wrapping it with back quotes: `` ` ``

![](https://raw.github.com/tiffon/sublime-to-done/master/img/note-emphasis.png)

```
-       Some title: This has a `special` note
```

## Task states

### Completed tasks

Completed tasks have a plus sign `+` in front of the first hyphen. The completed state can be toggled using the _"Toggle Comment"_ shortcut (`super+/` for Mac or `ctrl+/` for Linux and Windows). Any sub-tasks are automatically considered completed, as well.

![](https://raw.github.com/tiffon/sublime-to-done/master/img/task-state-completed.png)

```
+-      This is completed
        -       This sub task is considered completed, too
```

### Emergency tasks

**This is not yet implemented in the VSCode version of this plugin.**

Tasks can be emphasized by putting an exclamation mark `!` in front of the tasks first hyphen. This state is applied to any sub tasks.

![](https://raw.github.com/tiffon/sublime-to-done/master/img/task-state-emergency.png)

```
!-      This task is now considered dire
        -       So is this one, by association
```

### Cancelled tasks

Tasks can be dimmed to make them easier to ignore by putting a period `.` in front of the tasks first hyphen. A note about the cancellation can be defined by enclosing text in parentheses at the beginning of the title of the task. This state is applied to any sub tasks.

![](https://raw.github.com/tiffon/sublime-to-done/master/img/task-state-cancelled.png)

```
.-      (reason cancelled) Some title
        -       This is cancelled, too
```

## Goto

**This is not yet implemented in the VSCode version of this plugin.**
The goto menu (`super+r` on Mac) is set up to show only current tasks. Completed tasks and cancelled tasks are filtered out.

![](https://raw.github.com/tiffon/sublime-to-done/master/img/example-goto.png)

## Discussion Group

https://groups.google.com/forum/#!forum/to-done

