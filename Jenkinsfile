pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/architectdevops7/devops-terraform-cicd.git'
            }
        }

        stage('Terraform Init') {
            steps {
                sh 'terraform init'
            }
        }

        stage('Terraform Plan') {
            steps {
                sh 'terraform plan -out=tfplan'
            }
        }

        stage('Terraform Action') {
            steps {
                sh ("terraform ${action} -auto-approve tfplan")
            }
        }
    }
}
