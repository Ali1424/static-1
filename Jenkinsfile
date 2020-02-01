pipeline {
    agent any
    stages {
        stage('Lint HTML') {
            steps {
                sh 'echo Linting HTML'
                sh 'tidy -q -e *.html'
            }
        }
        stage('Upload to AWS') {
            steps {
                withAWS(region:'us-east-1', credentials: 'aws-static') {
                    s3Upload(file:'index.html', bucket:'tamas-udacity-project-jenkins', path:'index.html')
                }
            }
        }
        stage('Health check') {
            steps {
                curl 'http://tamas-udacity-project-jenkins.s3-website.us-east-1.amazonaws.com'
                }
            }
    }
}