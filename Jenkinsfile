pipeline {
    agent any

    stages {
        stage('Unit Tests') {
            steps {
                echo 'Testing..'
                sh 'ant -f test.xml -v'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'ant'
                sh 'ant -f build.xml -v'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('Report') {
            steps {
                echo 'Generating Report....'
            }
        }
    }
}
