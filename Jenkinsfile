pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
                sh 'g++ -c main/PES1UG20CS645.py'
                sh 'g++ -o PES1UG20CS645 main/PES1UG20CS645.cpp'            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
                sh './main/PES1UG20CS645'
                echo 'test stage successful'            }
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
