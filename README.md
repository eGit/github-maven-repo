# maven-repo-gradle-dev


1. clone maven-repo-gradle-dev from Github to HOME_DIR: 
  
  > git clone https://github.com/eGit/maven-repo-gradle-dev.git


2. git clone to Desktop: gradle-dev from Bitbucket and import projects to Eclipse (remove errors: gradle cleanEclipse eclipse)
3. Download the "complete" (includes sources) version of Gradle you want to add from: https://gradle.org/releases
    Extract downloaded Gradle distribution to HOME_DIR
    Edit gradle-dev/make/src/de/genflux/Build.java - especially GRADLE_VERSION (use version number of Gradle dist you just extracted)
4. Create gradle dist .jar and -sources.jar and copy to HOME_DIR/maven-repo-gradle-dev: 

  > gradle publishMyBigFatGradleJarPublicationToMyRepoRepository

5. check HOME_DIR/maven-repo-gradle-dev if everything worked

6. Commit and push repo updates to remote Github repo

git add -A

git commit -m "Adding new Gradle distribution"

git push


# Create maven repo in Gradle-Build (utilized by other project: gradle-init-java-project)

String url = "https://raw.githubusercontent.com/eGit/maven-repo-gradle-dev/master";

or

String url = "https://github.com/eGit/maven-repo-gradle-dev/raw/master";


java: make.getRepositories().maven(m -> m.setUrl(url));
groovy: maven { url "https://github.com/eGit/maven-repo-gradle-dev/raw/master" }

implementation "de.genflux:gradle-dev:5.4.1"

groovy: apply plugin: 'java'
kotlin: apply(plugin = "java")

groovy: plugins { id 'java' }
kotlin: plugins { id("java") }

The project "gradle-init-java-project" (alias jinit) uses the "maven-repo-gradle-dev" files to have jars and sources of Gradle directly in Eclipse 
so one can develop very complex Gradle builds purely in Java. Also one can use it to explore Gradle API in a proper IDE instead of a script.
