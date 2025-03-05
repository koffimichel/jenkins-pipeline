pipeline {
    agent any 
    stages{
        stage('clone'){
            steps{
                sh 'echo "clone"'
                sh 'uname -r'
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