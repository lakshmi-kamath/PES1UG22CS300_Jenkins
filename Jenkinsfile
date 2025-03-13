pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                branches: [[name: '*/main']],
                userRemoteConfigs: [[url: 'https://github.com/lakshmi-kamath/PES1UG22CS300_Jenkins.git']]])
            }
        }

        stage('Build') {
            steps {
                build 'PES1UG22CS300-1'
                sh 'g++ ./main/hello.cpp -o output'
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
