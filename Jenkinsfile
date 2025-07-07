pipeline {
    agent any
    stages {
        // stage('Checkout') {
        //     steps {
        //         git 'https://github.com/hoanglinhdigital/nodejs-random-color.git'
        //     }
        // }

        stage('Build') {
            steps {
                sh 'docker build -t nodejs-random-color:ver-lab7 .'
            }
        }
        stage('Upload image to ECR') {
            steps {
                sh 'aws ecr get-login-password --region ap-southeast-1 | docker login --username AWS --password-stdin 034362074955.dkr.ecr.ap-southeast-1.amazonaws.com'
                sh 'docker tag nodejs-random-color:ver-lab7 034362074955.dkr.ecr.ap-southeast-1.amazonaws.com/nodejs-random-color:ver-lab7'
                sh 'docker push 034362074955.dkr.ecr.ap-southeast-1.amazonaws.com/nodejs-random-color:ver-lab7'
            }
        }
    }
}
