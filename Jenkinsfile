pipeline {
    agent any 
    stages{
        stage('CodeSacn'){
            steps{
                sh 'trivy fs . -o result.html'
                
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