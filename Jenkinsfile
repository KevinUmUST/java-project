pipeline {
    agent any

    stages {
        stage('Unit Tests') {
            steps {
                echo 'Testing..'
                //sh 'which aws'
                sh 'curl "https://bootstrap.pypa.io/get-pip.py" -o "get-pip.py"'
                sh 'pip'
                
                sh 'ls /usr/bin'
                sh 'ant -f test.xml -v'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'ant -f build.xml -v'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh 'aws s3 cp dist/rectangle-${BUILD_NUMBER}.jar s3://assignment-10/rectangle-${BUILD_NUMBER}.jar'
            }
        }
        stage('Report') {
            steps {
                echo 'Generating Report....'
            }
        }
    }
}
