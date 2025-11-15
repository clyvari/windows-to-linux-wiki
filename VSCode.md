# VSCode
Containerized / isolated install for VSCode
Goal is to use vscode with devcontainers to isolate dev


### Install VSCode flatpack
`flatpak install flathub com.visualstudio.code`

### Configure permissions with FlatSeal
* ~~Uncheck `Filesystem > All system files`~~
* Add in `Filesystem > Other files`: `/tmp/vsch-$(whoami)`
* Add in `Persistent > Files`: `.local/bin`, `.vscode`
There might be other perms to change in order to harden VS

### Install VS Extensions:
* `Remote Development` pack (`WSL` + `Dev Containers` + `Remote SSH` + `Remote - Tunnels`)
* `Remote Explorer`
* `Remote - SSH: Editing Configuration Files`

### Install podman
* `sudo apt install podman`
* Enable socket: `systemctl --user enable --now podman.socket`, which creates `/var/run/user/$(id -u)/podman/podman.sock`

### Add podman scripts to VSCode:
* `~/.var/app/com.visualstudio.code/.local/bin/podman`:
  ```shell
  #!/bin/bash
  set -eu
  flatpak-spawn --host podman "$@"
  ```
* `~/.var/app/com.visualstudio.code/.local/bin/podman-compose`:
  ```shell
  #!/bin/bash
  set -eu
  flatpak-spawn --host podman-compose "$@"
  ```

### Configure VSCode
* `Extensions`
    * `Dev Containers`
        * `Docker Compose Path`: `/home/$(whoami)/.local/bin/podman-compose`
        * `Docker Path`: `home/$(whoami)/.local/bin/podman`
        * `Docker Socket Path`: `/run/user/$(id -u)/podman/podman.sock`

Don't actually use `$(...)` in the config, replace by the command value
