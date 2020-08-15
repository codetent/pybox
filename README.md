![Python package](https://github.com/codetent/pybox/workflows/Python%20package/badge.svg)

# PyBox

## Description

PyBox is a lightweight tool for bundling a pyz file in an exe file. If an executable is deployed, it can also be useful
to set an executable icon or additional metadata (product name, company name, versions, ...).

This project is really useful if the actual application is packed using ![shiv](https://github.com/linkedin/shiv) and then converted to an executable using PyBox.

## How does it work?

PyBox uses the fantastic python distlib launcher mentioned in ![PEP 397](https://www.python.org/dev/peps/pep-0397/).

First, the pylauncher is copied to the target path. Then the pyz file is appended to the launcher. Afterwards, an additional icon or metadata is set using ![rcedit](https://github.com/electron/rcedit) - a great project usually used for branding electron project.

## Usage

Install the latest pybox release using pip:

```
pip install pybox
```

Run pybox:

```
pybox <SOURCE>
    -c, --config VALUE:ExistingFile      Path to config file for setting additional metadata
    --gui                                Set to true, if source is a GUI application
    -i, --icon VALUE:ExistingFile        Path to exe icon
    --refresh                            Refresh Windows icon cache after building
    -t, --target VALUE:ExistingFile      Path to output file. If not set, the source path is taken
```

Example call:

```
pybox example.pyz --icon icon.ico --config app.cfg
```