#### This project is for the Devops bootcamp exercise for 
#### "Build Tools and Package Managers" 

<details>
<summary>Module 6 exercise: Gradle build and push to Nexus</summary>

#### added to build.gradle
```
apply plugin: 'maven-publish'

publishing {
    publications {
        maven(MavenPublication) {
            artifact("build/libs/build-tools-exercises-$version"+".jar"){
                extension 'jar'
            }
        }
    }

    repositories {
        maven {
            name 'nexus'
            url "http://64.227.104.254:8081/repository/maven-module6/"
            allowInsecureProtocol = true
            credentials {
                username project.repoUser
                password project.repoPassword
            }
        }
    }
}
```

#### added gradle.properties
```
repoUser = xxxxxx
repoPassword = xxxxxx
```
</details>