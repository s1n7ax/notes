# Neovim in Devcontainer

## What is Devcontainer?

- Development container is a container configured for development
- [Specification](https://containers.dev/implementors/spec/)
- [Devcontainer-cli](https://github.com/devcontainers/cli)

---

## Disclaimer

- You don't need Devcontainer to do development using Neovim inside a container

---

## Why Devcontainers?

- Reproducible development environment
- Reusable features
- Managing containers are easy
- Environment could be as simple as the base image or as complex as a compose file with multiple services
- ~~Support editor integration~~

---

## Can I use Neovim?

- Is there a terminal? Then yes
- Remote access to Neovim is possible

Server:

```shell
nvim --listen 0.0.0.0:8888 --headless
```

Client:

```shell
nvim --server localhost:8888 --remote-ui
```

---

## How to use Neovim

- Start the container

```
devcontainer up --workspace-folder .
```

- Start up Neovim

```
devcontainer exec --workspace-folder . nvim
```

---

## Challenges of Creating features

- Dependency of features?
- Features works only on the targeted base images
- No build logs on test success
