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
              {
                steps {
	   withMaven(jdk: 'JDK_HOME', maven: 'Maven_Home')
           sh 'mvn clean verify sonar:sonar'
}}
            }    
        }
