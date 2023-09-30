pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                git 'https://github.com/Diego-pgm/jenkins_docker.git'
                script{
                    docker build -t custom-nginx:"${env.BUILD_ID} ."
                }
            }
        }
        stage('Run'){
            steps{
                script{
                    docker run -p 80:80 --name custom-nginx:"${env.BUILD_ID}"
                }
            }
        }
    }
}