### Jenkins Shared Library for Java Maven Project

### Overview

This repository contains a Jenkins Shared Library that centralizes and automates common DevOps tasks for Java Maven applications.

By abstracting repetitive CI/CD steps into reusable functions, this library allows teams to maintain consistent build and deployment pipelines while reducing boilerplate code in Jenkinsfile.

Features

The library provides reusable functions for:

#### 1. Build Java Maven Application
Compiles the code
Generates the JAR artifact

#### 2. Docker Image Build
Builds Docker images from the generated JAR

#### 3. Docker Login
Authenticates to Docker registries securely

#### 4. Docker Push
Pushes images to the configured Docker registry

###Usage
#### 1. Add Shared Library in Jenkins

Go to Manage Jenkins → Configure System → Global Pipeline Libraries

#### Add the library:
#### Name: jenkins-shared-library
#### Git repository: https://github.com/Prashzan/jenkins-shared-library
#### Save configuration

#### 2. Example use in Jenkinsfile
   @Library('jenkins-shared-library') 
   
#### Directly into your Jenkinsfile instead of Jenkins UI
```
#!/usr/bin.env groovy
    library identifier: 'jenkins-shared-library@main', retriever: modernSCM(
    [$class: 'GitSCMSource',
    remote:'https://github.com/Prashzan/jenkins-shared-library.git',
    credentialsId: 'github-credentials']
)
```

