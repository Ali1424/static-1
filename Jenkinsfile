pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                withAWS(region:'us-east-1', credentials: AKIASRCXVIUT64CRZIOI) {
                    s3Upload(file:'index.html', bucket:'tamas-udacity-project-jenkins', path:'index.html')
                }
            }
        }
    }
}