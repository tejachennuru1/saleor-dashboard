jenkin to terraform calling using below script:-



pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            agent any
            steps {
                git branch: 'dev', url: 'https://github.com/WorkshopsByKhaja/saleor-dashboard.git'
            }
        }
        stage('docker image build') {
            agent any
            steps {
                sh 'docker image build -t shaikkhajaibrahim/saleor-dashboar:DEV .'
            }
        }
        stage('push image to registry') {
            agent { label 'build' }
            steps {
                sh 'docker image push shaikkhajaibrahim/saleor-dashboar:DEV'
            }
        }
        stage('create terraform infrastructre') {
            agent { label 'terraform' }
            steps {
                git url: 'git clone https://github.com/hashicorp/learn-terraform-provision-eks-cluster'
                sh 'terraform init && terraform apply -auto-approve'
            }
        }
    }
}
