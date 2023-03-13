pipeline {
    agent any    
    
    stages {
        stage('Git') {
            steps {checkout scmGit(branches: [[name: '*/main']], extensions: [cleanBeforeCheckout()], userRemoteConfigs: [[url: 'https://github.com/braemma2013/Jenkins-ci-cd-Project.git']])
                echo 'Checking out..'
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Deploy') {
            steps {deploy adapters: [tomcat9(credentialsId: '34754f07-11cd-4df8-8954-ff888e8110ae', path: '', url: 'http://18.234.199.142:8080/')], contextPath: null, war: '**/*.war'
                echo 'Deploying....'
            }
        }
    }
}
