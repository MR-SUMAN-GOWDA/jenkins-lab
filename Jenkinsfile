pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
		    build 'PES1UG23CS832-1'
                    echo 'Building the application...'
                    sh 'g++ hello.cpp -o hello_exec' // Compiling C++ file
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
                    sh './hello_exec' // Executing compiled C++ file
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying application...'
                    // You can replace the following line with actual deployment commands if required
                    echo 'Deployment step completed successfully.'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
