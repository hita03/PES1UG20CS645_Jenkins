pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
                sh 'g++ -c main/PES1UG20CS645.cpp'
                sh 'g++ -o PES1UG20CS645 main/PES1UG20CS645.cpp'
                build job: 'PES1UG20CS645-1'

            }
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
