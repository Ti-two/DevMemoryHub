# Task JSON

The tasks.json file in Visual Studio Code (VSCode) is used to automate common development tasks, such as:

    Compiling code (e.g., C, C++, TypeScript, etc.)
    Running a script or tool (e.g., make, gcc, npm run, etc.)
    Flashing a microcontroller (e.g., with openocd, st-flash, etc.)
    Running tests, linting, etc.

This file is part of VSCode's custom task configuration system and is typically located in the .vscode/ folder of the project.

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Build c file",
      "type": "shell",
      "command": "gcc",
      "args": ["-o", "main", "main.c"],
      "group": {
        "kind": "build",
        "isDefault": true
      },
      "problemMatcher": []
    }
  ]
}
```
Execute a task in VS code:
Ctrl+Shift+P > Run Task
#My task for STM32 project: makefile + Coretex-Debug
```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "build",
      "type": "shell",
      "command": "make",
      "args": [
        "all"
      ],
      "group": {
        "kind": "build",
        "isDefault": true
      },
      "options": {
        "cwd": "${workspaceFolder}/WIFI BLT F105 Debug"
      },
      "problemMatcher": [
        "$gcc"
      ],
      "isBackground": false
    },
    {
  "label": "Build STM32 F105 Debug",
  "type": "shell",
  "command": "bash",
  "args": [
    "-c",
    "make clean && make all -j4"
  ],
  "group": "build",
  "options": {
    "cwd": "${workspaceFolder}/WIFI BLT F105 Debug"
  },
  "problemMatcher": [
    "$gcc"
  ],
  "isBackground": false
}
  ]
}
``
