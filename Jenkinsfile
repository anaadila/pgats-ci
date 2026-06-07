pipeline {
    agent {
        label 'mestre'
    }

     tools {
        nodejs "node 24.16.0"
     }

     stages {

        stage('Build') {
            steps {
                bat 'npm install -g yarn'
                bat 'yarn install'
                bat 'yarn playwright install --with-deps'
            }
        }

        stage('Unity Tests') {
            steps {
                bat 'yarn run test'
            }
        }

        stage('E2E Tests') {
            steps {
                bat 'yarn run e2e'
            }
        }
     }
}