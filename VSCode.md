# VSCode
Containerized / isolated install for VSCode
Goal is to use vscode with devcontainers to isolate dev


### Install VSCode flatpack
flatpak install flathub com.visualstudio.code

### Configure permissions with FlatSeal
* Uncheck `Filesystem > All system files`
* Add in `Filesystem > Other files`: `/tmp/vsch-$(whoami)`
* Add in `Persistent > Files`: `.local/bin`, `.vscode`
There might be other perms to change in order to harden VS, but I havent'explored it yet
