https://github.com/MR-SUMAN-GOWDA/jenkins-lab.git
pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/MR-SUMAN-GOWDA/jenkins-lab.git']]
                ])
            }
        }

        stage('Build') {
            steps {
                build 'PES1UG23CS832-1'
                sh 'g++ main/hello.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline Failed!'
        }
    }
}
