# Neovim in Devcontainer

## What is Devcontainer & Devcontainer-cli?

- Development container is a container configured for development
- [Specification](https://containers.dev/implementors/spec/)
- [Devcontainer-cli](https://github.com/devcontainers/cli)

---

## Disclaimer

- You don't need Devcontainer to do development using Neovim inside a container

---

## Why Devcontainers?

- Reproducible development environment
- Easy to add features
- Managing containers are easy
- Environment could be as simple as the base image or as complex as a compose file with multiple services
- ~~Support editor integration~~

---

## Can I use Neovim?

- Is there a terminal? Then yes
- Remote access to Neovim is also possible but you need to handle the port mapping by yourself

```shell
# Server:
nvim --listen 0.0.0.0:8888 --headless
```

```shell
# Client:
nvim --server localhost:8888 --remote-ui
```

---

## How to use Neovim

- Create the devcontainer spec inside the project

```json
{
  "name": "spring boot container",
  "image": "ubuntu:latest",
  "features": {
    "ghcr.io/s1n7ax/devcontainer-features/jdk21:0": {},
    "ghcr.io/s1n7ax/devcontainer-features/neovim-essentials:0": {},
    "ghcr.io/s1n7ax/devcontainer-features/neovim:0": {},
    "ghcr.io/s1n7ax/devcontainer-features/astronvim:0": {}
  }
}
```

- Start the container

```
devcontainer up --workspace-folder .
```

- Start up Neovim

```
devcontainer exec --workspace-folder . nvim
```

## Other useful devcontainer options

- `--remove-existing-container` - to rebuilds the image

```shell
devcontainer up --workspace-folder . --remove-existing-container
```

- `--mount` - to mount neovim user config

```shell
devcontainer up --workspace-folder . --mount 'type=bind,source=/home/s1n7ax/.config/astronvim,target=/root/.config/astronvim'
```

- `--additional-features` - if you don't want to edit the `devcontainer.json` but want to use Neovim, use this flag to add additional features
- `--dotfiles-repository` - personalize the container with your dotfiles

---

## Challenges of Creating features

- Dependency of features?

  - `installsAfter` to mark dependencies of a feature but these will be ignored if `devcontainer.json` does not use theme

    ```json
    # devcontainer-feature.json
    "installsAfter": [
        "ghcr.io/s1n7ax/devcontainer-features/neovim-essentials:0",
        "ghcr.io/s1n7ax/devcontainer-features/neovim:0"
    ]
    ```

    ```json
    # devcontainer.json
    {
      "name": "Ubuntu image just for demo",
      "image": "ubuntu:latest",
      "features": {
        "ghcr.io/s1n7ax/devcontainer-features/jdk21:0": {},
        "ghcr.io/s1n7ax/devcontainer-features/neovim-essentials:0": {},
        "ghcr.io/s1n7ax/devcontainer-features/neovim:0": {},
        "ghcr.io/s1n7ax/devcontainer-features/astronvim:0": {}
      }
    }
    ```

    - It appears devcontainer supposed to be self contained?

- Features works only on the targeted base images
- No build logs on test success
