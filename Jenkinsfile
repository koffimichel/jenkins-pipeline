pipeline {

    agent any 
    stages {
        stage ('CodeScan') {
            steps {
                sh 'trivy fs . -o result.html'
                sh 'cat result.html'
              
                }
            }
            stage ('dockerLogin') {
            steps {
                sh 'aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 352415517565.dkr.ecr.us-east-1.amazonaws.com'
                }
            }
        stage ('dockerImageBuild') {
            steps {
                sh 'docker build -t jenjins-ci .'
                }
            }
            stage ('dockerImageTag') {
            steps {
                sh 'docker tag jenjins-ci:latest 352415517565.dkr.ecr.us-east-1.amazonaws.com/jenjins-ci:latest'
                }
            }
        stage ('pushImage') {
            steps {
                sh 'docker push 352415517565.dkr.ecr.us-east-1.amazonaws.com/jenjins-ci:latest'
                }
        }
    }
}