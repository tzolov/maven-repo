Install JAR
===
Place the JAR file in the local Git repository by letting Maven perform an install:
```
mvn install:install-file
 -DgroupId=[group-id]
 -DartifactId=[artifact-id]
 -Dversion=[version]
 -Dpackaging=[packaging-format]
 -Dfile=[path-to-file]
 -DlocalRepositoryPath=[path-to-git-repo]
``` 
* `[group-id]`, `[artifact-id]`, `[version]` and `[packaging-format]` define the Maven properties of the file to install.
* `[path-to-file]` - path to the JAR file to install.
* `[path-to-git-repo]` - path to the local Git repository on your computer.

After successful execution of the command a folder structure is created in the local Git repository. This structure and the files in it make it usable as a Maven repo. 
Commit the changes, that were made by executing the Maven install command, to the local Git repository. Publish the updated repository to GitHub. The JAR file is now ready to be used in a Maven POM file.

Use maven-repo
==========
Add the tzolov GitHub maven repository to the POM file of the project:
```
<repository>
    <id>git-tzolov</id>
    <name>tzolov's Git based repo</name>
    <url>https://github.com/tzolov/maven-repo/raw/master/</url>
</repository>
```
