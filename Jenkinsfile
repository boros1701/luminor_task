pipeline {
    agent any
    tools { 
        gradle 'Gradle'  
    }
    stages {
        stage ('Checkout from scm') {
            steps {
                checkout scmGit(branches: [[name:'*/master']], extensions: [[]], userRemoteConfig: [[url: 'https://github.com/boros1701/luminor_task.git']])
            }
        }

        stage ('Build') {
            steps {
                sh 'gradlew clean build docker'
            }
        }

        stage ('Test') {
            steps {
                sh 'gradle test'
            }
        }
    }
}
