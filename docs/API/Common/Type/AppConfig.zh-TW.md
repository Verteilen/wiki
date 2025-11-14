# AppConfig

應用程式配置 <br />
顯示目前 App 的配置 <br />
透過後端定義 proxy 工作者

## Property

#### isExpress: boolean

> FLAG: Express <br />
> 影響瀏覽器行爲, 查看是否使用 Express 作爲後端

#### isElectron: boolean

> FLAG: Electron <br />
> 影響瀏覽器行爲, 查看是否使用 Electron 作爲後端

#### isAdmin: boolean

> FLAG: Admin <br />
> 如果是運算伺服器, 查看用戶權限是否爲管理員

#### haveBackend: boolean

> FLAG: Backend <br />
> 影響瀏覽器行爲, 是否有後端 <br />
> 如果爲否, 代表現在是靜態伺服器 <br />
> 所有邏輯將在瀏覽器上執行

#### login:boolean

> 登入狀態 <br />
> 給 Express 伺服器模式偵測狀態

#### backendType: BackendType

> 伺服器類型 <br />
> 詳細查看 [這裡](../Enum/BackendType.zh-TW.md)