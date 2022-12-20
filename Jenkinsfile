pipeline {
    agent any

    stages {
        stage('vcs') {
            steps {
                git branch:'main',
                  url:'https://github.com/tejachennuru1/saleor-dashboard.git'
            }
        }

        stage('build') {
            steps {
                sh 'docker image build -t tejachennuru1/saleor-dashboard:Dev .'
            }
        }
                stage('push image to registry') {
                    steps {
                        sh 'docker image tag  tejachennuru1/saleor-dashboard:Dev tejaaws/saleor-dashboard:Dev'
                        sh 'docker image push tejaaws/saleor-dashboard:Dev'
                        sh 'docker container run -d -P tejaaws/saleor-dashboard:Dev '
                    }
                }
    }
}
