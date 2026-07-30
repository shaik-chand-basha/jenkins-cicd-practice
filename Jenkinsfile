pipeline {
    agent any


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
            steps {
                echo 'Setting up the environment'
                // git clone https://github.com/shaik-chand-basha/jenkins-cicd-practice.git git_project
            }
        }
        stage('Build') {
            steps {
                echo 'Building the project'
                // cd git_project && ./build.sh
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests'
                // cd git_project && ./test.shs
            }
        }
    }
    post {
            always {
                echo 'Cleaning up'
                // rm -f git_project/
            }
            success {
                echo 'Build and tests succeeded'
            }
            failure {
                echo 'Build or tests failed'
            }
    }
}
