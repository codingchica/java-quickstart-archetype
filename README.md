# Java Quickstart Archetype
This project is a Maven archetype to generate a new Maven-based Java project.  

## Testing Locally
To test changes to the archetype locally run:
```shell
mvn clean \
    install \
    archetype:generate \
    -DarchetypeGroupId="com.codingchica.maven.archetypes" \
    -DarchetypeArtifactId="java-quickstart-archetype" \
    -DarchetypeVersion="0.1-SNAPSHOT" \
    -DgroupId="testgroup" \
    -DartifactId="testartifact" \
    -Dversion="0.1-SNAPSHOT" \
    -DoutputDirectory=target/testartifact \
    --batch-mode; \
    mvn clean \
    install \
    -DbaseDir="target/testartifact"
```

## Generating a New Project
To consume the archetype and create a new project:
```shell
# Within the parent directory where you want the project to be created
mvn clean \
    install \
    archetype:generate \
    -DarchetypeGroupId="com.codingchica.maven.archetypes" \
    -DarchetypeArtifactId="java-quickstart-archetype" \
    -DarchetypeVersion="0.1-SNAPSHOT" \
    -DoutputDirectory=<ThisShouldBeTheParentDirectoryToWhereYouWantTheNewProjectCreated>
```