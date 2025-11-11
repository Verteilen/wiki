# Project Structure

``` mermaid
---
title: Overview
---
graph LR
    A{share codebase} -->|copy to| B[Program]
    A -->|copy to| C[Compute Node]
    A -->|copy to| D[Web]
    A -->|copy to| E[Electron]
    A -->|copy to| F[Express]
    B -->|build| G((EXE))
    G -.->|needs| C
    G -.->|needs| E
    G -.->|needs| F
    D -->|build| H((HTML))
    E -->|build| I((msi, deb Files))
    F -->|build| J((NodeJS Files))
    style G fill:#f7d899
    style H fill:#f7d899
    style I fill:#f7d899
    style J fill:#f7d899
    style A fill:#eccafc
```

## Share

It's a codebase which share in different application

!!! info "Source code path location"
    It's locate at src/share

!!! message ""Share" Action"
    Which start copy the code into different folder
    ```bash
    npm run share
    ```

!!! warning "Modify Notice"
    So if you want to modify the core logic<br />
    You should modify the content in the src/share <br />
    Example: <br />
    If you edit the code in src/main/client/.... <br />
    After share command, your modify action will be gone

## Worker

The executable program which run the task logic on it.<br />
This program is called by runner. In order to implement multithread logic in NodeJS environment

!!! info "Source code path location"
    It's locate at src/program
    The program entry point is src/program/worker.ts

!!! message "Build program"
    Use command below to package the program to executable file
    ```bash
    # Build exe depend on current os
    npm run pkg
    # Build worker.exe which run on windows
    npm run pkg win
    # Build worker.exe which run on mac
    npm run pkg mac
    # Build worker.exe which run on linux
    npm run pkg linux
    ```
    The output will locate at ./bin folder

!!! warning "Clean build application warning"
    If you have multiple executable in the bin folder <br />
    And you build the electron application or express application <br />
    They will copy the entire bin folder, which means it will copy the unnecessary files to output <br />
    <b>Make sure delete bin folder before build any runner application</b>

## Runner

### Static Web

Simple task management host by browser, which it close when user close browser <br />
It's unreliable you could said, But easy deploy

Notices:

- [ ] Backend
- [ ] Playground
- [ ] Authentication

!!! info "Source code path location"
    It's locate at src/renderer

!!! message "Build html"
    Use command below to use vite package the renderer to html files
    ```bash
    # Output html files
    npm run build:web
    ```
    The output will locate at ./build/renderer folder

### Electron Application

Notices:

- [x] Backend
- [x] Playground
- [ ] Authentication

!!! info "Source code path location"
    Frontend locate at src/renderer
    Backend locate at src/main

!!! message "Build electron"
    Use command below to package the electron app to installation files
    ```bash
    # Build electron app depend on current os
    npm run build
    # Build electron app which run on windows (.msi)
    npm run build:win
    # Build electron app which run on mac
    npm run build:mac
    # Build electron app which run on linux (.deb)
    npm run build:linux
    ```
    The output will locate at ./dist folder

### Express Server

Notices:

- [x] Backend
- [x] Playground
- [x] Authentication

It's nodejs express server which hosting the backend

!!! info "Source code path location"
    Frontend locate at src/renderer
    Backend locate at src/server

!!! message "Build express"
    Use command below to package the express to nodejs deploy files
    ```bash
    # Output nodejs files
    npm run build:server
    ```
    The output will locate at ./build/server folder

### Compute Node

It's the client side application, it recevied server signal and do the calculation then return the info etc... <br />
It runs without user interface

!!! info "Source code path location"
    It's locate at src/node

!!! message "Build node"
    Use command below to package the express to nodejs deploy files
    ```bash
    # Output nodejs files
    npm run build:node
    ```
    The output will locate at ./build/node folder