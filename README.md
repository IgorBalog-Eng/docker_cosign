# GitHub Workflow example project

![diagram](doc/github actions workdlow.drawio.png?raw=true "GitHub Workflow diagram")

.github\workflows\ folder, check for specific GHA file:

## feature_hotfix.yml

Used when code is pushed to branch prefixed with feature/ or hotfix/

Customize GHA to fit your needs. For now, just run mvn clean package

## develop.yml

Executed when code is pushed to develop branch.

## maven_release.yml

Manual trigger of the GHA.</br>
Perform mvn release:prepare and mvn release:perform.

Input parameters:</br>
release version</br>
next development version</br>
tag version

## docker-publish.yml

Manual trigger of the GHA.</br>
Build docker image, and push it to dockerhub.</br>
Sign with cosign.

Input parameters:<br/>
versionName<br/>
tagMessage

## snyk.yml

Manual trigger of the GHA.

Execute snyk code analysis for security vulnerabilities.

Pre-requisite:<br/>
Create account in snyk.io<br/>
Get snyk API token from Account Settings<br/>
Copy it and create new Action secret - SNYK_TOKEN
