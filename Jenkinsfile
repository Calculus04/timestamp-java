pipeline {
    agent any
    
    environment {
        PATH = "${JAVA_HOME}/bin:${PATH}"
    }
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Verify Java') {
            steps {
                sh 'echo $JAVA_HOME'
                sh 'java -version'
            }
        }
        
        stage('Compile') {
            steps {
                sh 'javac TimeStamp.java'
            }
        }
        
        stage('Run') {
            steps {
                sh 'java TimeStamp'
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline execution failed!'
        }
    }
}