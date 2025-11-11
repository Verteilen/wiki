# 專案結構

``` mermaid
---
title: 大綱
---
graph LR
    A{verteilen_core} -->|依賴於| B[Program]
    A -->|依賴於| C[Compute Node]
    A -->|依賴於| D[Web]
    A -->|依賴於| E[Electron]
    A -->|依賴於| F[Express]
    A -->|依賴於| K[Cluster]
    B -->|建置| G((EXE))
    D -->|建置| H((HTML))
    E -->|建置| I((msi, deb Files))
    F -->|建置| J((NodeJS Files))
```

<br /><br />

``` mermaid
---
title: 執行依賴
---
graph LR
    B((EXE))
    C[Compute Node]
    E[Electron]
    F[Express]

    B -.->|依賴於| C
    B -.->|依賴於| E
    B -.->|依賴於| F
```

## 共享

共享到名個專案的腳本

!!! info "原始碼連結"
    連結附上於 [Verteilen-Core](https://github.com/Verteilen/Verteilen-Core)

!!! message ""更新" 動作"
    更新核心庫
    ```bash
    # 會將下載的核心庫版本打印出來
    npm i verteilen-core && cat package.json | grep core
    ```

## 工作者

這個執行檔將會用於流程的運算 <br />
透過執行者呼叫, 生成 Thread 實體, 爲了在 NodeJS 環境實現多核心

!!! info "原始碼連結"
    連結附上於 [here](https://github.com/Verteilen/worker)

!!! message "建置程式"
    用以下指令進行打包
    ```bash
    # 根據目前作業系統打包
    npm run pkg
    # 打包 Window 平台用執行檔
    npm run pkg win
    # 打包 MacOS 平台用執行檔
    npm run pkg mac
    # 打包 Linux 平台用執行檔
    npm run pkg linux
    ```
    輸出會在 ./bin 資料夾

## 執行者

### 靜態網頁

Simple task management host by browser, which it close when user close browser <br />
It's unreliable you could said, But easy deploy

Notices:

- [ ] Backend
- [ ] Playground
- [ ] Authentication

!!! info "Source code location"
    It's locate at [Verteilen](https://github.com/Verteilen/Verteilen) <br />
    Currently official Github page repository is [Here]([Static-Web](https://github.com/Verteilen/.github))

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
    Frontend locate at src/renderer <br />
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


### Cluster