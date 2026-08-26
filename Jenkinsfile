pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build Image'){
            steps {
                docker build -t team-skeleton:${BUILDER_NUMBER} .
            }
        }
        stage('Test') {
            steps {
                sh 'mvn -B test'
                junit 'target/surefire-reports/*.xml'
            }
        }
    }
}