# INSTRUCTIONS TO CONFIGURE JCSHELL SCRIPTING LANGUAGE ON VISUAL STUDIO CODE

1. Copy `jcsh` directory to `%USERPROFILE%\.vscode\extensions`.
2. Restart Visual Studio Code.
3. Configure a new task in your [tasks.json](tasks.json) file (Terminal>Configure tasks). Don't forget to change the base path for JCShell _twice_.

    ```[json]
    {
        "type": "shell",
        "label": "Run .jcsh script",
        "command": "d:/tools/jcshell/5.17/jcshell.bat",
        "args": [
            "-v",
            "-x",
            "-d",
            "-f",
            "${file}"
        ],
        "group": {
            "kind": "build",
            "isDefault": true
        },
        "presentation": {
            "reveal": "always",
            "focus": false,
            "echo": true,
            "showReuseMessage": false,
            "panel": "new",
            "clear": false,
        },
        "options": {
            // very important: without this scripts won't run as expected ie. won't print apdus
            "cwd": "d:/tools/jcshell/5.17"
        },
        "runOptions": {},
        "problemMatcher": []
    }
    ```

4. Open a script .jcsh and run it from Terminal > Run task.

## Sources

- [Instructions for creating a custom language](https://stackoverflow.com/a/32996211/2692914).
- [Configure language ie. to comment line](https://code.visualstudio.com/api/language-extensions/language-configuration-guide).
- [Task configuration ie. to run jcsh script](https://code.visualstudio.com/docs/editor/tasks).
- [JCShell language definition](https://github.com/NXPmicro/JCShell-Tools).
- [Configure keybindings ie. Idea keybindings](https://code.visualstudio.com/docs/getstarted/keybindings)
