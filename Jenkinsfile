pipeline {
    agent any
    stages {
        stage('checking') {
            steps {
                git branch: 'main' url: 'https://github.com/Juho-source/timecalctest_jenkins.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }