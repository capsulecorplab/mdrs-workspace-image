# MDRS Workspace (Kasm Image)

![Screenshot from 2023-06-09 09-48-15](https://github.com/capsulecorplab/mdrs-workspace-image/assets/14095576/0f7832dd-5ae3-4dba-8250-717fce19c81f)

## Introduction

This repo provides an Immutable-Infrastructure-as-Code (IIaC) workspace for the Mars Desert Research Station (MDRS) based on the [Ansible based template for KASM Ubuntu Focal Images](https://github.com/j-simmons-phd/kasm-core-focal-template) template provided by @j-simmons-phd.  The workspace is configured with the following software:

- git cli
- [Keychain](https://www.funtoo.org/Keychain)
- Chrome
- Python 3.8.x (part of the image template) with the following packages (not part of the image template)
    - pip
    - [JupyterLab](https://jupyter.org/)
    - [Jupyter Notebook](https://jupyter.org/)
    - [Voilà](https://voila.readthedocs.io/en/stable/index.html)
    - [Pint](https://pint.readthedocs.io/en/stable/)
- VS Code with the following extensions (note, auto-updates are disabled)
    - [Python extension by Microsoft](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
    - [Dendron](https://marketplace.visualstudio.com/items?itemName=dendron.dendron)
    - [Foam](https://marketplace.visualstudio.com/items?itemName=foam.foam-vscode)
- Artifact Generators
    - [PlantUML](https://plantuml.com/)
        - JDK v11
        - Graphviz 2.50 (built from source)
    - [AsciiDoctor](https://asciidoctor.org/) v2.0.17 with PlantUML and PDF support

## Requirements

1. A Bash terminal ([Ubuntu on WSL2](https://ubuntu.com/tutorials/install-ubuntu-on-wsl2-on-windows-11-with-gui-support#2-install-wsl) recommended for Windows users).
2. [Docker Compose](https://docs.docker.com/compose/install/) ([Docker Desktop](https://docs.docker.com/desktop/) recommended for non-Linux users)

## Setup/Installation

From a bash terminal,

1. Clone this repo

```bash
git clone https://github.com/capsulecorplab/mdrs-workspace-image.git
```

2. Change directory into `mdrs-workspace-image`.

```bash
cd mdrs-workspace-image
```

3. Run `docker-compose pull` (Note: Linux users may need to prepend this command with `sudo`) to pull the published version of the workspace image or run `docker-compose build` to build the image locally.

## Using the image locally

Once pulled or built, the image can be run locally on port 6901 using docker-compose.

- **Starting the image locally:** Run `docker-compose up`
- **Stopping the image locally:** Use keyboard shortcut **Ctrl+C**

When running locally, the workspace can be accessed at https://localhost:6901 with
- **User:** `kasm_user`
- **Passwordd:** `password`
