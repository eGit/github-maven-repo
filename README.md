# github-maven-repo


1. clone gradle-dev-maven from Github to HOME_DIR: 
  
  > git clone https://github.com/eGit/github-maven-repo.git


2. git clone to Desktop: gradle-dev from Bitbucket and import projects to Eclipse
3. Edit gradle-dev/make/src/de/genflux/Build.java - especially GRADLE_VERSION
4. Create gradle dist .jar and -sources.jar and copy to HOME_DIR/github-maven-repo: 

  > gradle tasks publishMyBigFatGradleJarPublicationToMyRepoRepository

5. check HOME_DIR/github-maven-repo if everything worked

6. Commit and push repo updates to remote Github repo

git add -A

git commit -m "Adding new Gradle distribution"

git push


# Create maven repo in Gradle-Build

String url = "https://raw.githubusercontent.com/eGit/github-maven-repo/master";

or

String url = "https://github.com/eGit/github-maven-repo/raw/master";


java: make.getRepositories().maven(m -> m.setUrl(url));
groovy: maven { url "https://github.com/eGit/github-maven-repo/raw/master" }

groovy: apply plugin: 'java'
kotlin: apply(plugin = "java")

groovy: plugins { id 'java' }
kotlin: plugins { id("java") }
