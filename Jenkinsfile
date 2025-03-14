pipeline {
    agent any
    stages {
        stage ('cCodeScan') {
            steps {
                sh 'trivy fs . -o result.html'
                 sh 'trivy fs . -o result.html'

            }
        }
        stage ('dockerImageBuild') {
            steps {
                sh 'docker -v'
            }
        }
        stage ('pushImage') {
            steps {
                sh 'docker ps'
            }
        }
    }
 
}