`vivaldi-autoinject-custom-js-ui` - manage custom js UI mods for the vivaldi web browser

SYNOPSIS
--------
```text
vivaldi-autoinject-custom-js-ui [--remove|-r FILENAME] [FILES ...]
vivaldi-autoinject-custom-js-ui --list|-l
vivaldi-autoinject-custom-js-ui --help|-h
vivaldi-autoinject-custom-js-ui --version|-v
```

DESCRIPTION
-----------
To manually add custom javascript modifications
to the **vivaldi** web browser one needs to do the
following:

- Add the javascript file to vivaldis resource directory (on arch this is `/opt/vivaldi/resources/vivaldi`)

- Add an entry in the browser.html file in the same directory.


This is not too complicated, but I have noticed
that when **vivaldi** is being updated, the
`browser.html` file is overwritten, meaning that
step 2 needs to be repeated after every update.  

It also gets a bit messy to manage multiple mods.  

If `vivaldi-autoinject-custom-js-ui` is launched
without any command line arguments, it will update
the `browser.html` file to include all javascript
files located in `PREFIX/share/vivaldi-UI-js`,
(*PREFIX will be inherited by the Makefile on
installation, but defaults to:* `/usr`). The
**vivaldi-UI-js/** directory is automatically
created by the script when new mods are added.

Any files with `.js` extension passed as
arguments will get added or updated.  

To remove a mod, pass the filename of the mod to
the `--remove` option.

If the script is executed on **Arch** Linux, it
will install a pacman hook (**alpm-hooks(5)**)
that will execute the script everytime vivaldi is
being updated.


OPTIONS
-------

`--remove`|`-r` FILENAME  
Remove FILENAME.

`--list`|`-l`  
Prints all installed js modifications.

`--help`|`-h`  
Show help and exit.

`--version`|`-v`  
Show version and exit.


DEPENDENCIES
------------
`bash`
`sed`
`vivaldi`


