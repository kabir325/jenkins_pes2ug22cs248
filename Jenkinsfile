pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'g++ main/hell.cpp -o build_output'
            }
        }
        stage('Test') {
            steps {
                sh './build_output'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Deploying application..."'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline Failed'
        }
    }
}
