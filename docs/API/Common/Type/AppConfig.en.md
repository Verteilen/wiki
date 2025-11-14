# AppConfig

Application Configuration <br />
Show current state of the app <br />
Defined by the backend proxy worker

## Property

#### isExpress: boolean

> FLAG: Express <br />
> For browser check if it's connect to a express server

#### isElectron: boolean

> FLAG: Electron <br />
> For browser check if it's use Electron desktop app currently

#### isAdmin: boolean

> FLAG: Admin <br />
> If use express server, check user have root permission

#### haveBackend: boolean

> FLAG: Backend <br />
> For browser check if it's connect to any server <br />
> If false, it means it's a static website <br />
> All the logic will run on browser

#### login:boolean

> Login state <br />
> For express mode detect only

#### backendType: BackendType

> Server Type <br />
> Detail check [Here](../Enum/BackendType.en.md)