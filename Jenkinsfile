pipeline {
    agent any
    tools {
        maven "mvn"
    }
    stages {
        stage('SCM checkout')
                { steps { git branch : 'master', url: 'https://github.com/vinayak-95/simple-java-maven-app'}}
        
        stage('Build Artifact') {
            steps {
                withMaven(jdk: 'JDK_HOME', maven: 'mvn') {
                sh 'mvn package'
}
}
        }
    }
}
