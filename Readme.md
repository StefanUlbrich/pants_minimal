# Description

This repository contains a minimal example for the problem described [here](https://github.com/pantsbuild/pants/issues/20097).

The template resource is not included in the package.

```sh
pants package projects/minimal:pkg
tar tvzf dist/minimal-0.0.1.tar.gz
drwxr-xr-x  0 tdkt   staff       0 Oct 26 12:05 minimal-0.0.1/
-rw-r--r--  0 tdkt   staff      12 Oct 26 12:05 minimal-0.0.1/MANIFEST.in
-rw-r--r--  0 tdkt   staff      81 Oct 26 12:05 minimal-0.0.1/PKG-INFO
-rw-r--r--  0 tdkt   staff     762 Oct 26 12:05 minimal-0.0.1/backend_shim.py
drwxr-xr-x  0 tdkt   staff       0 Oct 26 12:05 minimal-0.0.1/minimal/
-rw-r--r--  0 tdkt   staff       0 Oct 26 12:05 minimal-0.0.1/minimal/__init__.py
drwxr-xr-x  0 tdkt   staff       0 Oct 26 12:05 minimal-0.0.1/minimal.egg-info/
-rw-r--r--  0 tdkt   staff      81 Oct 26 12:05 minimal-0.0.1/minimal.egg-info/PKG-INFO
-rw-r--r--  0 tdkt   staff     220 Oct 26 12:05 minimal-0.0.1/minimal.egg-info/SOURCES.txt
-rw-r--r--  0 tdkt   staff       1 Oct 26 12:05 minimal-0.0.1/minimal.egg-info/dependency_links.txt
-rw-r--r--  0 tdkt   staff       1 Oct 26 12:05 minimal-0.0.1/minimal.egg-info/namespace_packages.txt
-rw-r--r--  0 tdkt   staff       8 Oct 26 12:05 minimal-0.0.1/minimal.egg-info/top_level.txt
-rw-r--r--  0 tdkt   staff      38 Oct 26 12:05 minimal-0.0.1/setup.cfg
-rw-r--r--  0 tdkt   staff     353 Oct 26 12:05 minimal-0.0.1/setup.py
```

However, it works if the resource is in a subdirectory of the sources:

```sh
git checkout working
pants package projects/minimal:pkg
tar tvzf dist/minimal-0.0.1.tar.gz
drwxr-xr-x  0 tdkt   staff       0 Oct 26 11:08 minimal-0.0.1/
-rw-r--r--  0 tdkt   staff      12 Oct 26 11:08 minimal-0.0.1/MANIFEST.in
-rw-r--r--  0 tdkt   staff      81 Oct 26 11:08 minimal-0.0.1/PKG-INFO
-rw-r--r--  0 tdkt   staff     762 Oct 26 11:08 minimal-0.0.1/backend_shim.py
drwxr-xr-x  0 tdkt   staff       0 Oct 26 11:08 minimal-0.0.1/minimal/
-rw-r--r--  0 tdkt   staff       0 Oct 26 11:08 minimal-0.0.1/minimal/__init__.py
drwxr-xr-x  0 tdkt   staff       0 Oct 26 11:08 minimal-0.0.1/minimal/templates/
-rw-r--r--  0 tdkt   staff      10 Oct 26 11:08 minimal-0.0.1/minimal/templates/tmpl.yaml
drwxr-xr-x  0 tdkt   staff       0 Oct 26 11:08 minimal-0.0.1/minimal.egg-info/
-rw-r--r--  0 tdkt   staff      81 Oct 26 11:08 minimal-0.0.1/minimal.egg-info/PKG-INFO
-rw-r--r--  0 tdkt   staff     248 Oct 26 11:08 minimal-0.0.1/minimal.egg-info/SOURCES.txt
-rw-r--r--  0 tdkt   staff       1 Oct 26 11:08 minimal-0.0.1/minimal.egg-info/dependency_links.txt
-rw-r--r--  0 tdkt   staff       1 Oct 26 11:08 minimal-0.0.1/minimal.egg-info/namespace_packages.txt
-rw-r--r--  0 tdkt   staff       8 Oct 26 11:08 minimal-0.0.1/minimal.egg-info/top_level.txt
-rw-r--r--  0 tdkt   staff      38 Oct 26 11:08 minimal-0.0.1/setup.cfg
-rw-r--r--  0 tdkt   staff     420 Oct 26 11:08 minimal-0.0.1/setup.py
```
