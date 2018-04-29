pipeline {
    agent {label 'a0ebf93d9816'}
    
    stages {
        stage('Unit Tests') {
            steps {
                echo 'Testing..''
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
                sh 'aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins'
            }
        }
    }
}
