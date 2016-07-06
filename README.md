# phing-task

A collection of Phing Tasks.

# Installation

[Composer](http://getcomposer.org/):

```json
{
  "require": {
    "yalesov/phing-task": "2.*"
  }
}
```

[Phing](https://github.com/phingofficial/phing) is **not** bundled with this package.

You can install it through Composer and use the CLI at `vendor/bin/phing`:

```json
{
  "require": {
    "phing/phing": "*"
  }
}
```

or through PEAR and use the CLI at `phing`:

```sh
$ pear channel-discover pear.phing.info
$ pear install [--alldeps] phing/phing
```

# Usage

## ClassmapTask

Generate a classmap for the directory `foo/library` (and its subdirectories), save it at `foo/autoload_classmap.php`.

```xml
<project>
  <target>
    <includepath classpath="vendor/yalesov/phing-task/src/task" />
    <taskdef name="classmap" classname="ClassmapTask" />
    <classmap dir="foo/library" output="foo/autoload_classmap.php" />
  </target>
</project>
```

## ClassmapClearTask

Clear the classmap file `foo/autoload_classmap.php`, i.e. set it to `return array();`.

```xml
<project>
  <target>
    <includepath classpath="vendor/yalesov/phing-task/src/task" />
    <taskdef name="classmap-clear" classname="ClassmapClearTask" />
    <classmap-clear file="foo/autoload_classmap.php" />
  </target>
</project>
```

## RchownTask

Recursively [chown](http://php.net/manual/en/function.chown.php) the directory `foo/src`, along with all its subdirectories and files, to the user `foouser` and group `foogroup`.

```xml
<project>
  <target>
    <includepath classpath="vendor/yalesov/phing-task/src/task" />
    <taskdef name="rchown" classname="RchownTask" />
    <rchown file="foo/src" user="foouser.foogroup" />
  </target>
</project>
```

## Rrmdir

Recursively [rmdir](http://php.net/manual/en/function.rmdir.php) the directory `foo/src`, along with all its subdirectories and files.

```xml
<project>
  <target>
    <includepath classpath="vendor/yalesov/phing-task/src/task" />
    <taskdef name="rrmdir" classname="RrmdirTask" />
    <rrmdir file="foo/src" />
  </target>
</project>
```
