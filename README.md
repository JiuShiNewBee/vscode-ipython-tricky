# vscode-ipython-tricky
come on baby

## Only first line is run in the ipython terminal??
Solution:
1. Download extension: macros
2. Edit 'settings.json'
```json
    "macros": {
        "runSelIpython": [
            "editor.action.clipboardCopyAction",
            {"command": "workbench.action.terminal.paste"},
            {"command": "workbench.action.terminal.sendSequence", "args": {"text": "\u000d"}},
            {"command": "workbench.action.terminal.sendSequence", "args": {"text": "\u000d"}},
            {"command": "workbench.action.terminal.sendSequence", "args": {"text": "\u000d"}},
        ]
    },
```
3. Add keybinding in 'keybindings.json'
```json
    {
        "key":"cmd+r",
        "command":"macros.runSelIpython",
    }
```
4. If it does not work, I do not know :)
   It works for me.
