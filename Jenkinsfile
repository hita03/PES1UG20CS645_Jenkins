pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
                sh 'g++ main/task5.cpp'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
                sh './a.out
            }
        }

        stage('Deploy') {
            steps {
                sh 'deploy.sh'
            }
        }
    }

    post {
        always {
            sh 'echo "Pipeline completed"'
        }

        failure {
            sh 'echo "Pipeline failed"'
        }
    }
}
