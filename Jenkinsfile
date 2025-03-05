pipeline {
    agent any 
    stages{
        stage('CodeSacn'){
            steps{
                sh 'trivy --version'
                
            }
        }
        stage('docker(mageBuild)'){
            steps{
                sh 'docker -v'
            }
        }
        stage('pushImage')
            steps{
                sh 'docker ps'
            }
        }  
}