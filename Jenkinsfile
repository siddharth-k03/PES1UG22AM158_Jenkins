pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    sh 'git clone https://github.com/PES1UG22AM158_Jenkins.git'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    sh 'g++ -o PES1UG22AM158-1 hello.cpp'
                    echo 'Build Stage Successful'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh './PES1UG22AM158-1'
                    echo 'Test Stage Successful'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh 'git add .'
                    sh 'git commit -m "Added new .cpp file and build"'
                    sh 'git push origin main'
                    echo 'Deployment Successful'
                }
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
