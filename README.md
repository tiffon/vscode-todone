# ToDone

## This is very much a work in progress. 

Unfortunately, I've ran into an issue I've been unable to circumvent, so far:

> [How to customize the color of custom syntax tokens in VSCode extension](https://stackoverflow.com/questions/46377151/how-to-customize-the-color-of-custom-syntax-tokens-in-vscode-extension)

As a result, the only way I know of to apply the colors for the grammar are through user settings. So, if the extension is installed, user settings then need to be updated.

The good news is: That works. But, it's not exactly a smooth installation process, so I haven't published this extension.

## What it looks like



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

