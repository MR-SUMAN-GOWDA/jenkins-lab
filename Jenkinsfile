pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                branches: [[name: '*/main']],
                userRemoteConfigs: [[url: 'https://github.com/MR-SUMAN-GOWDA/jenkins-lab.git']]])
            }
        }

        stage('Build') {
            steps {
                script {
                    echo "🛠 Compiling C++ program..."
                    sh 'g++ main/main.cpp -o output'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo "✅ Running the compiled program..."
                    sh 'chmod +x output'
                    sh './output'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo "🚀 Deployment Step - Modify as needed"
                }
            }
        }
    }

    post {
        failure {
            script {
                echo "❌ Pipeline failed! Check logs for errors."
            }
        }
    }
}
