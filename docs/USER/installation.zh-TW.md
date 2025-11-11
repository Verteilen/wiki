# 安裝

## 靜態網頁

你不需要安裝任何東西, 你可以按 [這裡](https://verteilen.github.io/.github/) 直接使用

!!! warning "沒有進階功能"
    靜態網頁等於沒有後台 <br />
    這會侷限於只有核心的功能而已

!!! warning "瀏覽器不能關"
    在運算結束前, 你不能關閉瀏覽器 <br />
    否則所有的節點會離線, 因爲瀏覽器持有所有你本地的 Websocket 連線

## 運算節點安裝

安裝 nodejs 全局插件來使用運算節點 <br />

```bash
# 安裝
npm install -g verteilen_node
# 這指令來執行運算節點
verteilen_node
```
!!! node "第一次運作"
    如果你是第一次執行節點 <br />
    你會先下載執行的元件

## 中繼節點安裝

安裝 nodejs 全局插件來使用中繼節點 <br />

```bash
# 安裝
npm install -g verteilen_cluster
# 這指令來執行中繼節點
verteilen_cluster
```

## 伺服器安裝

安裝 nodejs 全局插件來使用伺服器 <br />

```bash
# 安裝
npm install -g verteilen_server
# 這指令來執行伺服器
verteilen_server
```
!!! node "第一次運作"
    如果你是第一次執行伺服器 <br />
    你會先下載執行的元件

## 桌面應用程式安裝

在 [釋出版本](https://github.com/Verteilen/Verteilen/releases) 頁面

* Windows 用戶 點擊 **.msi** 安裝檔
* Linux 用戶 點擊 **.deb** 安裝檔

## Docker 部署

快速部署運算節點 Docker

```bash
docker run --restart=always -p 12080:12080 --name verteilen_node0 e87870823/verteilen_node
```

快速部署伺服器 Docker

```bash
docker run --restart=always -p 11080:11080 -p 11777:11777 --name verteilen_server0 e87870823/verteilen_server
```