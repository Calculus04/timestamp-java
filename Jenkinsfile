pipeline {
    agent any
    
    environment {
        PATH = "${JAVA_HOME}\\bin;${PATH}"
    }
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Verify Java') {
            steps {
                bat 'echo %JAVA_HOME%'
                bat 'java -version'
            }
        }
        
        stage('Compile') {
            steps {
                bat 'javac TimeStamp.java'
            }
        }
        
        stage('Run') {
            steps {
                bat 'java TimeStamp'
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