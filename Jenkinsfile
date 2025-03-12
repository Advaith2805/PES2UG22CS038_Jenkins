pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'ls -l main'  // List files inside the "main" folder
                    sh 'g++ -o main/hello_exec main/hello.cpp'  // Compile hello.cpp
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh './main/hello_exec'  // Run the compiled program
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying application...'
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
