pipeline {
    agent any
	tools {
              jdk "JAVA_HOME"
	      maven "MAVEN_HOME"
        }

    stages {
        stage('Checkout') {
            steps {
checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'devopsdeepdive', url: 'https://github.com/devopsdeepdive/maven-pipeline.git']]])            }
        }
    
     stage('validate') {
            steps {
                sh 'mvn validate'
        }
    }
    
     stage('compile') {
            steps {
                sh 'mvn compile'
        }
    }
      stage('test') {
            steps {
                sh 'mvn test'
        }
    }
     stage('package') {
            steps {
                sh 'mvn package'
        }
    }
	}
}
