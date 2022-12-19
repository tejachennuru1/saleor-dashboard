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
                        sh 'docker image push -t:tejachennuru1 tejaaws/saleor-dashboard:Dev'
                    }
                }
    }
}
