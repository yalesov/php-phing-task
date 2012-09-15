# phing-task

A collection of Phing Tasks.

# Installation

[Composer](http://getcomposer.org/):

```json
{
    "require": {
        "heartsentwined/phing-task": "1.*"
    }
}
```

# Usage

## RchownTask

Recursively [chown](http://php.net/manual/en/function.chown.php) the directory `foo/src`, along with all its subdirectories and files, to the user `foouser` and group `foogroup`.

```xml
<project>
    <target>
        <includepath classpath="vendor/heartsentwined/phing-task/src/task" />
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
        <includepath classpath="vendor/heartsentwined/phing-task/src/task" />
        <taskdef name="rrmdir" classname="RrmdirTask" />
        <rrmdir file="foo/src" />
    </target>
</project>
```
