pipeline {
    agent {
        docker {
            image 'docker:26.1.4-cli'
            args '''
              -u root
              -v /var/run/docker.sock:/var/run/docker.sock
              -e DOCKER_CONFIG=/tmp/.docker
            '''
        }
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/vinaypotharaju96-bit/devops-cicd-pipeline.git',
                    credentialsId: 'github-token'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t cicd-app:latest .'
            }
        }
    }
}
