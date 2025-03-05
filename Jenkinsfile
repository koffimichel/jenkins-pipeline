pipeline {
    agent any 
    stages{
        stage('clone'){
            steps{
                sh 'echo "clone"'
            }
        }
        stage('test'){
            steps{
                sh 'echo "test"'
            }
        }
        stage('cratefile'){
            steps{
                sh 'touch text-$BUID_ID'
            }
        }
    }
}