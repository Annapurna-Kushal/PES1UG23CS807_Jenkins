pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: 'main']], 
                    userRemoteConfigs: [[url: 'https://github.com/Annapurna-Kushal/PES1UG23CS807_Jenkins.git']]
                ])
            }
        }
        stage('Build') {
            steps {
                build 'PES1UG23CS807-1'
                sh 'g++ ./main/hello.cpp -o ./output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
