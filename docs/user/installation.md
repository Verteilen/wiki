# Installation

## Static Web

Which you do not need to install anything, you can just click [here](https://verteilen.github.io/.github/) to use it

!!! info "No Advanced Features"
    Static Web mode means there is no backend attach to it <br />
    It will only contain core feature

!!! warning "Browser Cannot Close"
    You cannot close browser, before your task finish <br />
    All the compute node will disconnect, because all the websocket instance is hold in the browser code

## Compute Node Install

Install the nodejs module in the global for compute node <br />
use npm install the compute tool node


```bash
npm install -g verteilen_node
# use command ctn to start the client
verteilen_node
```
!!! node "First time running"
    If you're running verteilen_node the first time <br />
    It will trying to download the worker executable first


## Desktop App Install

In [Release](https://github.com/Verteilen/Verteilen/releases) page

* For windows user click **.msi** installation file
* For linux user click **.deb** installation file

## Docker Install

Here is the quick deploy for compute node docker container

```bash
docker run --restart=always -p 12080:12080 --name verteilen_node0 e87870823/verteilen_node
```

Here is the quick deploy for compute server docker container

```bash
docker run --restart=always -p 11080:11080 -p 11777:11777 --name verteilen_server0 e87870823/verteilen_server
```