pipeline {
    agent any
    stages {
        stage ('cCodeScan') {
            steps {
                sh 'trivy --version'

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