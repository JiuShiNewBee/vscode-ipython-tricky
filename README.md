# vscode-ipython-tricky
come on baby

## 1. Only the first selected line is run in the ipython terminal??
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
   
##### 1. does not work for the new python version?  
Solution:
Try multi-command:
```json
    "multiCommand.commands": [
        {
            "command": "multiCommand.run",
            "sequence": [
                "editor.action.clipboardCopyAction",  
                "workbench.action.terminal.paste", 
                {"command": "workbench.action.terminal.sendSequence", "args": {"text": "\u000d"}},
            ]
        }
    ],
```
## 2. Matlab deep dog-licker? however your money is robbed?
Solution:
1. Download vscode
2. Download ipython
3. Open vscode 
4. Type ctrl + ` 
5. Run ipython
6. Enjoy travelling through the black-hole
7. If it does not work, I do not know :) 
   Do not try jupyter-book, do not try, do not..., do, d
