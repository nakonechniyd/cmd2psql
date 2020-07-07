# cmd2psql - is a syntax surag for calling psql commands from editor

passwords for databases should be placed in `.pgpass`

## Visual Studio Code 

### install extention:
- [Command Runner](https://marketplace.visualstudio.com/items?itemName=edonet.vscode-command-runner)


### copy project-cmd2psql to your path:
update values: HOST,USERNAME,DBNAME
```
cp project-cmd2psql $HOME/.local/bin
```


### add these lines to settings.json:

```
"command-runner.commands": {
    "psql-in-tab": "echo \"${selectedText}\" | project-cmd2psql | code - &",
    "psql-in-terminal": "echo \"${selectedText}\" | project-cmd2psql"
}
```

### add keyboard shortcut
```
{
    "key": "ctrl+k ctrl+enter",
    "command": "command-runner.run",
    "args": {
        "command": "psql-in-tab",
        "terminal": "psql"
    }
}
```

