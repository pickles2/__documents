# Package Naming Conventions

## Applications

- Pickles 2
    - repository: pickles2/app-pickles2
    - renamed from `Pickles 2 Desktop Tool` to `Pickles 2`.
- Asazuke 2
    - repository: pickles2/app-asazuke2
- Morizke 2
    - repository: pickles2/app-morizke2
- Other Applications
    - Pickles 2 Web Tool (Web Application)
        - repository: pickles2/app-pickles2-webtool
    - Asazuke 2 SiteScan
        - repository: pickles2/app-pickles2-sitescan
    - YoungCorn (deprecated)
        - repository: pickles2/app-youngcorn

## Pickles 2 Project Preset

- repository:
    - pickles2/preset-{$template\_name}
- composer package:
    - pickles2/preset-{$template\_name}
- Get Start Pickles 2
    - repository: pickles2/preset-get-start-pickles2
    - composer package: pickles2/preset-get-start-pickles2
- Other
    - Pickles 2 (deprecated)
        - pickles2/pickles2

## Pickles Framework Core

- composer package:
    - pickles2/px-fw-2.x
    - pickles2/asazuke-fw-2.x
    - pickles2/morizke-fw-2.x

### Pickles 2 plugin packages

- repository: px2-{$plugin\_name}
- composer package: pickles2/px2-{$plugin\_name}

### Pickles 2 theme packages

- repository: pickles2/px2-theme-{$theme\_name}
- composer package: pickles2/px2-theme-{$theme\_name}


## broccoli HTML Editor Core

- npm package: broccoli-html-editor
- repository: broccoli-html-editor/broccoli-html-editor

### broccoli-html-editor module packages

- repository:
    - broccoli-html-editor/broccoli-module-{$module\_name}
    - pickles2/broccoli-module-{$module\_name}
- composer package:
    - broccoli-html-editor/broccoli-module-{$module\_name}
    - pickles2/broccoli-module-{$module\_name}
- npm package: broccoli-module-{$module\_name}

### broccoli-html-editor field packages

- repository: broccoli-field-{$field\_name}
- composer package: broccoli-html-editor/broccoli-field-{$field\_name}
- npm package: broccoli-field-{$field\_name}

## Other libraries examples

### npm package

- repository: node-px2agent
- npm package: px2agent
