pipeline {
    agent any

    stages {
        stage('Setup') {
            steps: {
            echo 'Setting up the environment'
            sh 'git clone https://github.com/shaik-chand-basha/jenkins-cicd-practice.git git_project'
            sh 'ls'
            }
        }
        stage('Build') {
            steps: {
            echo 'Building the project'
            sh 'cd git_project && ./build.sh'
            }
        }
        stage('Test') {
            steps: {
            echo 'Running tests'
            sh 'cd git_project && ./test.sh'
            }
        }
        post {
            always {
                echo 'Cleaning up'
                sh 'rm -rf git_project'
            }
            success {
                echo 'Build and tests succeeded'
            }
            failure {
                echo 'Build or tests failed'
            }
        }
    }
}
