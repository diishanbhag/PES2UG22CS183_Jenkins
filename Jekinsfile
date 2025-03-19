pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo "Building Stage"
                sh 'make -C main'
                sh 'echo "Build Stage Successful"'
            }
        }
        
        stage('Test') {
            steps {
                echo "Testing Stage"
                sh 'cd /var/jenkins_home/workspace/${JOB_NAME}/main/ && ./hello_exec'
                sh 'echo "Test Stage Successful"'
            }
        }
        
        stage('Deploy') {
            steps {
                echo "Deployment Stage"
                sh 'echo "Deploying the application..."'
                sh 'echo "Deployment Stage Successful"'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed'
        }
        success {
            echo 'Pipeline succeeded'
        }
    }
}
