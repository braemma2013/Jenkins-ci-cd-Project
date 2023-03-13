pipeline {
    agent any

    stages {
        stage('Code Checkout from version control') {
            steps {checkout scmGit(branches: [[name: '*/main']], extensions: [cleanBeforeCheckout()], userRemoteConfigs: [[url: 'https://github.com/braemma2013/Jenkins-ci-cd-Project.git']])
                echo 'Building..'
            }
        }
        stage('Build') {
            steps {build 'CalculatorwebApp'
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
