# Installation

## Static Web

Which you do not need to install anything, you can just click [here](https://verteilen.github.io/.github/) to use it

The problem is that because there is no backend attach to it, so it will lack alot of feature for it
And the server will shutdown when user close the browser

## Node Install

Install the nodejs module in the global for compute node\
use npm install the compute tool node

```bash
npm install -g verteilen_node
# use command ctn to start the client
verteilen_node
```


## Desktop App

In [Release](https://github.com/Verteilen/Verteilen/releases) page

* For windows user click .msi installation file, 
* For linux user click .deb installation file

## Docker Install

Here is the quick deploy for compute node docker container

```bash
docker run --restart=always -p 12080:12080 --name verteilen_node0 e87870823/verteilen_node
```

Here is the quick deploy for compute server docker container

```bash
docker run --restart=always -p 11080:11080 -p 11777:11777 --name verteilen_server0 e87870823/verteilen_server
```