pipeline {
    agent any

    stage('Unit Tests') {
        steps {
            echo 'Testing..'
            //sh 'ant -f test.xml -v'
        }
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                //sh 'ant'
                //sh 'ant -f build.xml -v'
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
