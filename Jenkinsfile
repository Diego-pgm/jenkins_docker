pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                git 'https://github.com/Diego-pgm/jenkins_docker.git'
                script{
                    docker.build("custom-nginx:${env.BUILD_ID}")
                }
            }
        }
        stage('Run'){
            steps{
                script{
                    docker.image("custom-nginx:${env.BUILD_ID}").run('-p 80:80')
                }
            }
        }
    }
}