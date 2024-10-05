pipeline {
    agent any 
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from SCM
                git url: 'https://github.com/sarraai/SpringIOC', credentialsId: 'your-credentials-id'
            }
        }
        stage('Build') {
            steps {
                // Run your build commands here
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                // Run your tests
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                // Deploy your application
                sh 'echo "Deploying application..."'
            }
        }
    }
}
