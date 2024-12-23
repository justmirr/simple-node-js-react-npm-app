pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'npm install'
            }
        }

        stage('test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }

        stage('deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'finished using the website? (click \'proceed\' to continue!)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}