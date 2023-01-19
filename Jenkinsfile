pipeline {
    agent any

    stages {
        
        stage('Deleting old container') {
            steps {
                sh 'docker rm -f httpd'
            }
        }
        stage('Delete old image') {
            steps {
                sh 'docker rmi '
            }
        }
        stage('Create Docker image') {
            steps {
                sh 'docker build -t testingpipeline:v1 .'
            }
        }
        
        stage('Create a container') {
            steps {
                sh 'docker run -d --name httpd -p 82:80 testingpipeline:v1'
            }
        }
        
        
    }
}
