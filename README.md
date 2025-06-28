# LaTeX DevContainer

Are you:

- Writing a thesis in Overleaf?
- Hitting compile time limits?
- Having your eyes burnt by looking at the theme/font you don't like?
- Not able to track changes with Git?
- Missing global cross-file search & replace, multicursors and all your other editor goodies?

Dev Containers will be your friend then! This setup allows you to write your LaTeX documents from within a Dev Container. Recommended setup is [VS Code](https://code.visualstudio.com/) + [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## How to use

1. Install [VS Code](https://code.visualstudio.com/) and [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers).
2. Copy `.devcontainer` into your project.
3. Reopen your project with selecting `Remote-Containers: Reopen in Container` from VS Code Command Pallette (`CTRL+SHIFT+P`).
4. Open any of your `.tex` files and click "Build" icon.

Optionally you can also copy `.vscode/settings.json`. It contains:

- basic Overleaf-like setup for compiling PDFs,
- hides some temporary files from the project navigation,
- configures the extension to recompile PDF on file save,
- sets the default formatter to [`tex-fmt`](https://github.com/WGUNDERWOOD/tex-fmt).

## Using Git

You can use `git` as usual (almost). The dev container should already have your `.gitconfig` copied into container on startup (so no need to set `user.name` and `user.email` again). 

The only caveat is that you might not be able to `git push` from within the container. In short, this requires additional setup, see the VS Code [docs](https://code.visualstudio.com/remote/advancedcontainers/sharing-git-credentials) about this. When using SSH keys for Git operations within the Dev Container, additional setup of [SSH agent forwarding](https://code.visualstudio.com/remote/advancedcontainers/sharing-git-credentials#_using-ssh-keys) is required. Refer to docs on how to do that.

Once SSH agent forwarding is enabled, on the host add your key to the agent with `ssh-add <path_to_key>`, then verify the key is added with `ssh-add -l`. Once key is present in the agent, start your Dev Container. You can also verify that the key is accessible from within the container, again with `ssh-add -l`.

The Dev Container's `Dockerfile` also includes [Git LFS](https://git-lfs.com/) for storing images/other non-text files more efficiently. Refer to said Git LFS page to learn more and configure it accordingly (it's easy and takes a minute). It's already configured for `*.jpg` and `*.png` (see `.gitattributes`).

---

> Credits to https://github.com/James-Yu/LaTeX-Workshop/tree/master/samples/docker for example & VSC extension.
