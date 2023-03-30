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
           mvn clean verify sonar:sonar \
          -Dsonar.projectKey=My-test-project \
          -Dsonar.host.url='http://15.207.98.178:9000' \
          -Dsonar.login=squ_90d695fa4df5189ded061fd39fe4ad69dd4321d2
}}
            }    
        }
