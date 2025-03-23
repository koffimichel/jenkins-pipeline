pipeline {

    agent any 

    environment {
        AWS_REGION = 'us-east-1'
        IMAGE_ECR_REPO = '352415517565.dkr.ecr.us-east-1.amazonaws.com/jenjins-ci'
        ECR_REPO = '352415517565.dkr.ecr.us-east-1.amazonaws.com'
    }

    stages {
        stage ('CodeScan') {
            steps {
                sh 'trivy fs . -o result.html'
                sh 'cat result.html'
              
                }
            }
            stage ('dockerLogin') {
            steps {
                sh "aws ecr get-login-password --region $AWS_REGION | docker login --username AWS --password-stdin $ECR_REPO"
                }
            }
        stage ('dockerImageBuild') {
            steps {
                sh 'docker build -t jenjins-ci .'
                sh 'docker build -t imageversion .'
                }
            }
            stage ('dockerImageTag') {
            steps {
                sh "docker tag jenjins-ci:latest $IMAGE_ECR_REPO:latest"
                sh "docker tag imageversion $IMAGE_ECR_REPO:v1.$BUILD_NUMBER"
                }
            }
        stage ('pushImage') {
            steps {
                sh "docker push $IMAGE_ECR_REPO:latest"
                sh "docker push $IMAGE_ECR_REPO:v1.$BUILD_NUMBER"
                }
        }
    }
}