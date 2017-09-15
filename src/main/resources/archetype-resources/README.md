# Sample java maven project

This project is used as a startup/template project for java based projects using [jgitver-maven-plugin](https://github.com/jgitver/jgitver-maven-plugin) for version handling.

Off the shelf, it provides:
- unit testing with junit
- project versioning using [jgitver](https://github.com/jgitver/jgitver) via [jgitver-maven-plugin](https://github.com/jgitver/jgitver-maven-plugin)

## Build

__Standard build with unit testing__

- `mvn clean install`

__Release with SNAPSHOT version protection__

- `mvn -Prelease install`

## Release

Once your are satisfied of the HEAD commit (ie you performed all your tests)

- `git tag -a -m "release X.Y.Z, additionnal reason" X.Y.Z``
- `mvn -Prelease -DskipTests deploy`
- `git push --follow-tags origin master`