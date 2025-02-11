pipeline {
    agent any
    
    tools {
        // Configure JDK in Jenkins Global Tool Configuration
        jdk 'JDK17'
    }
    
    stages {
        stage('Checkout') {
            steps {
                // Get code from GitHub repository
                checkout scm
            }
        }
        
        stage('Compile') {
            steps {
                // Compile Java program
                sh 'javac TimeStamp.java'
            }
        }
        
        stage('Run') {
            steps {
                // Run the program and capture output
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