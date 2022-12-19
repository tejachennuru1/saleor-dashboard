pipeline {
    agent any
    triggers {
    }

    stages {
        stage('vcs') {
            steps {
                git branch: 'master',
            url: 'https://github.com/tejachennuru1/saleor-dashboard.git'
            }
        }

        stage('build') {
            steps {
                sh 'docker image build -t tejachennuru1/saleor-dashboard:Dev .'
            }
        }
    }
}
