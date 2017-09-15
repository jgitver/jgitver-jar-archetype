# jgitver-jar-archetype

Ready to use maven archetype generating basic java project with jgitver support.

## Generated project content:

- simple java project
- versioning using [jgitver](https://github.com/jgitver/jgitver-maven-plugin)
- unit testing with junit
  
## Usage

simply call `mvn archetype:generate -Dfilter=fr.brouillard.oss:jgitver-jar-archetype` and follow instructions

## Development

use `mvn archetype:generate -DarchetypeCatalog=local -Dfilter=fr.brouillard.oss:jgitver-jar-archetype` to use only archetypes built locally and thus avoid to retrieve remote versions

## Release

- `mvn -Poss clean install`: this will simulate a full build for oss delivery (javadoc, source attachement, GPG signature, ...)
- `git tag -a -s -m "release X.Y.Z, additionnal reason" X.Y.Z`: tag the current HEAD with the given tag name. The tag is signed by the author of the release. Adapt with gpg key of maintainer.
    - Matthieu Brouillard command:  `git tag -a -s -u 2AB5F258 -m "release X.Y.Z, additionnal reason" X.Y.Z`
    - Matthieu Brouillard [public key](https://sks-keyservers.net/pks/lookup?op=get&search=0x8139E8632AB5F258)
- `mvn -Poss,release -DskipTests deploy`
- `git push --follow-tags origin master` 