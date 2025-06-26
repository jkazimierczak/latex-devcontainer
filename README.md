# LaTeX DevContainer

Are you:
- Writing a thesis in Overleaf? 
- Hitting compile time limits? 
- Having your eyes burnt by looking at the theme/font you don't like? 
- Not able to track changes with Git?

Dev Containers will be your friend then! This setup allows you to write your LaTeX documents from within a Dev Container. Recommended setup is [VS Code](https://code.visualstudio.com/) + [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## How to use

1. Install [VS Code](https://code.visualstudio.com/) and [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers).
2. Copy `.devcontainer` into your project.
3. Reopen your project with selecting `Remote-Containers: Reopen in Container` from VS Code Command Pallette (`CTRL+SHIFT+P`).
4. Open any of your `.tex` files and click "Build" icon.

Optionally you can also copy `.vscode/settings.json`. It contains basic Overleaf-like setup for compiling PDFs and hides some temporary files from the project navigation. It also configs the extension to rebuild output PDF on file save.

## Using Git

You can use `git` as usual. The dev container should already have your `user.name` and `user.email` set, given these were configured on the host.

The Dev Container's `Dockerfile` also includes [Git LFS](https://git-lfs.com/) for storing images/other non-text files more efficiently. Refer to said Git LFS page to learn more and configure it accordingly (it's easy and takes a minute). It's already configured for `*.png` (see `.gitattributes`).

---

> Credits to https://github.com/James-Yu/LaTeX-Workshop/tree/master/samples/docker for example & VSC extension.
