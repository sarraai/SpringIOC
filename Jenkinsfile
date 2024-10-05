pipeline {
    agent any
    
    tools {
        // Ensure Maven is installed and configured in Jenkins
        maven 'M2_HOME'  
    }
    
    stages {
        stage('Git Checkout') {
            steps {
                // Checkout the Git repo
                git url: 'https://github.com/sarraai/SpringAOP.git', branch: 'main'
            }
        }
        
        stage('Maven Build') {
            steps {
                // Build the project using Maven
                sh 'mvn clean install'
            }
        }
        
        stage('Maven Test') {
            steps {
                // Run tests using Maven
                sh 'mvn test'
            }
        }
    }
    
    post {
        always {
            // Archive results even if build fails
            archiveArtifacts artifacts: 'target/*.jar', allowEmptyArchive: true
            junit 'target/surefire-reports/*.xml'  // Corrected path to ensure proper matching
        }
    }
    
    options {
        timestamps()  // To show time details
    }
}
