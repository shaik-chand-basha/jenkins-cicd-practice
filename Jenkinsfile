pipeline {
    agent any

    triggers {
        cron('H/5 * * * *')
    }

    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Branch to build')

        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

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
