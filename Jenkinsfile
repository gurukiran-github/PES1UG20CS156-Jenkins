pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ -o PES1UG20CS156-1 PES1UG20CS156-1.cpp'
            }
        }

        stage('Test') {
            steps {
                sh './PES1UG20CS156-1'
            }
        }

        stage('Deploy') {
            steps {
                ec 'deployed successfully'
            }
        }
    }

    post {
        always {
            script {
                if (currentBuild.result == 'FAILURE') {
                    echo 'pipeline failed'
                }
            }
        }
    }
}
