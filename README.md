# Phing Plugin for stakkr-org/stakkr
Plugin made to run [phing](https://www.phing.info/) on the current directory

__WARNING: The plugin directory must be named `phing`__ (complete path: plugins/phing)

# Installation
Clone the repository in the plugins/ directory of your stakkr
```bash
$ cd plugins/
$ git clone https://github.com/stakkr-org/stakkr-phing phing
$ stakkr refresh-plugins
```

# phing command
The `stakkr phing` command must be launched from the directory that contains the **build.xml** file. See the [Phing Documentation](https://www.phing.info/) about how to build that file.

As the report is generated inside a container, the permissions are set to root, to be able to delete the report folder,
do the following as the final task in your `build.xml`:
```xml
    <!-- As we use a docker image, make the current user able to read / delete the report -->
    <chmod file="report" mode="0777" />
```
