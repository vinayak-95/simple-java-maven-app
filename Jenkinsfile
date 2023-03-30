pipeline {
    agent any
    stages {
        stage('SCM checkout')
                { steps { git branch : 'master', url: 'https://github.com/vinayak-95/simple-java-maven-app'}}
        
        stage('Build Artifact') {
            steps {
                withMaven(jdk: 'JDK_HOME', maven: 'Maven_Home') {
                sh 'mvn clean package'
}
            }}
        stage('Sonar analysis') 
             { environment { SCANNER_HOME = tool 'sonar-scanner' } {
                steps {
                  withSonarQubeEnv(credentialsId: 'Sonar-Token', installationName: 'SonarQube') {
                      sh '${SCANNER_HOME}sonar:sonar'
}}
            }    
        }
    }
