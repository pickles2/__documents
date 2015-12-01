# Package Naming Conventions

## Pickles2 plugin packages

- repository: px2-{$plugin\_name}
- composer package: pickles2/px2-{$plugin\_name}

## Pickles2 theme packages

- repository: px2-theme-{$theme\_name}
- composer package: pickles2/px2-theme-{$theme\_name}

## broccoli-html-editor field packages

- repository: broccoli-field-{$field\_name}
- composer package: pickles2/broccoli-field-{$field\_name}
- npm package: broccoli-field-{$field\_name}

## broccoli-html-editor module packages

- repository: broccoli-module-{$module\_name}
- composer package: pickles2/broccoli-module-{$module\_name}
- npm package: broccoli-module-{$module\_name}

## Applications examples

- composer package: pickles2/pickles2
- repository: youngcorn
- repository: pickles2desktoptool

## Other libraries examples

### Pickles Framework Core

- composer package: pickles2/px-fw-2.x

### broccoli HTML Editor Core

- npm package: broccoli-html-editor

### npm package

- repository: node-px2agent
- npm package: px2agent


### pickles2 Map
![pickles2 Map](http://g.gravizo.com/g?
digraph pickles2_Map {
aize ="4,4";
Applications, pickles2, youngcorn, pickles2desktoptool;
Applications -> pickles2;
Applications -> youngcorn;
Applications -> pickles2desktoptool;
pickles2, plugin, theme, "broccoli HTML Editor Core";
pickles2 -> plugin;
pickles2 -> theme;
pickles2 -> "broccoli HTML Editor Core";
youngcorn, "broccoli HTML Editor Core", field, module;
youngcorn -> "broccoli HTML Editor Core";
"broccoli HTML Editor Core" -> field;
"broccoli HTML Editor Core" -> module;
"Other libraries", "Pickles Framework Core", "broccoli HTML Editor Core", "npm package";
"Other libraries" -> "Pickles Framework Core";
"Other libraries" -> "broccoli HTML Editor Core";
"Other libraries" -> "npm package";
}
)
