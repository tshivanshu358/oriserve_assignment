pipeline {
    agent any
    tools {
        go 'go1.21.13' // Specifying the Go version
    }

    stages {
        stage('Build') {
            steps {
                sh 'go mod download'
                sh 'go build -o main main.go'
            }
        }

        stage('Package') {
            steps {
                sh 'zip my-application.zip main index.html'
            }
        }
        stage('Upload to S3') {
            steps {
            
                sh 'aws s3 cp my-application.zip s3://oriserve-assessment/'
                
            }
        }
    }
}        
