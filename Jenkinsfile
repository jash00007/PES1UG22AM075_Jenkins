pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ -o output program.cpp'
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    // Introduce an error (invalid command to cause failure)
                    sh './invalid_output' 
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Application...'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed'
        }
    }
}
