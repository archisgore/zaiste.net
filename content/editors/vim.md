+++
title = "Vim"
[extra]
howtos = true
+++

Vim 8 added a native way to load 3rd party plugins. Thus, there is no need any longer to use things like `pathogen`.

Create `~/.vim/pack/<any-name>/start/` - this will hold all plugins and Vim will automatically pick up any packages added to this folder.

Optionally, `/.vim/pack/<any-name>/opt/` may be created for packages that won't be loaded automatically. Those packages can be loaded manually using `:packadd <package-name>`.

