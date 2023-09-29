pipeline {
    agent any
  
    stages {
        stage('Clone repo') {
            steps {
                // Checkout source code from version control
                git url: 'https://github.com/YASHODA-MUNNANGI/jenkins_docker2.git',
                    credentialsId: 'guthub',
                    branch: 'main'
            }
        }
        
        stage('Docker Build') {
            steps {
                // Build the Docker image
                script {
                    sh 'docker build -t my-app:0.1 -f Dockerfile .'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                // Deploy the Docker container
                script {
                    sh 'docker run -it -p 8080:8082 --name my-app-container my-app:0.1'
                }
            }
        }
    }
}
