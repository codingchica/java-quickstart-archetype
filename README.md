# Java Quickstart Archetype
[![Java CI with Maven](https://github.com/codingchica/java-quickstart-archetype/actions/workflows/maven.yml/badge.svg)](https://github.com/codingchica/java-quickstart-archetype/actions/workflows/maven.yml)

This project is a Maven archetype to generate a new Maven-based Java project.  

## Testing Locally
To test changes to the archetype locally run the following from within the `java-quickstart-archetype` folder.
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
    --batch-mode
    
mvn clean \
    install \
    -DbaseDir="target/testartifact"
```

## Generating a New Project
At present, there is no published package.  Therefore, you must clone this git repo and build it locally before it 
can be used to create new Java projects. 

To consume the archetype and create a new project:
```shell
# Find the desired parent folder for java-quickstart-archetype
cd <parent Directory Of Where You Want the java-quickstart-archetype folder created> 

# Clone the Git repo locally
git clone https://github.com/codingchica/java-quickstart-archetype.git

# Go into the new java-quickstart-archetype folder
cd java-quickstart-archetype

# Build the archetype locally and then create a new project from this archetype template in interactive mode.
# The install command builds the archetype and puts it into your local Maven artifact cache.
# The archetype:generate command is what will then create a new project from the archetype template.
mvn install \
    archetype:generate \
    -DarchetypeGroupId="com.codingchica.maven.archetypes" \
    -DarchetypeArtifactId="java-quickstart-archetype" \
    -DarchetypeVersion="0.1-SNAPSHOT" \
    -DoutputDirectory=<ThisShouldBeTheParentDirectoryToWhereYouWantTheNewProjectCreated>
```
