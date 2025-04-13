pipeline {
    agent any
    tools{
        git "Git-2.43.0"
    }
    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/pavankamuju/practice.git'
            }
        }
        stage('maven build') {
            steps{
                sh'mvn clean package'
            }
        }
        stage('docker image') {
            steps{
                sh 'docker build -t krishnakamuju/mavenwebapp .'
            }
        }
        stage('k8s deploy'){
            steps{
                sh'kubectl apply -f k8s-deploy.yml'
            }
        }
    }
}
