pipeline {
    agent any
    tools {
        maven 'maven3'
        jdk 'jdk8'
    }
    stages {
        stage('Code Validate') {
            steps {
                sh 'mvn validate'
            }
        }
        stage('Code Compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('Code Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Packing') {
            steps {
                sh 'mvn package'
            }
        }
    }
    post {
      success{
          junit 'target/surefire-reports/*.xml'
      }
 
    }
    }

