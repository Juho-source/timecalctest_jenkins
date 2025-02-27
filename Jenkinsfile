pipeline {
    agent any
    stages {
        stage('checking') {
            steps {
                git branch: 'main', url: 'https://github.com/Juho-source/timecalctest_jenkins.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test & coverage') {
            steps {
                sh 'mvn test jacoco:report'
            }
            post {
                always {
                junit 'target/surefire/*.xml'
                jacoco execPattern: '**/target/jacoco.exec',
                       classPattern: '**/target/classes',
                       sourcePattern: '**/src/main/java',
                       exclusionPattern: '**/test/**'
                       }
                }


    }
}