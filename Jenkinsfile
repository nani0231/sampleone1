pipeline {
    agent any
    stages {
        stage('Test') {
            when {
                anyOf {
                    branch 'production'
                    branch 'testing'
                    branch 'development'
                }
            }
            steps {
                sh 'mvn test'
            }
        }
      stage('Build') {
            when {
anyOf{
                branch 'production'
                    branch 'testing'
                    branch 'development'
                }            }
            steps {
                sh 'mvn package'
            }
        }
        stage('Deploy to Production') {
            environment {
                TOMCAT_URL = 'http://3.0.176.113:8080'
                TOMCAT_USER = 'tomcat'
                TOMCAT_PASSWORD = 'tomcat'
         
            }
            when {
                branch 'production'
            }
                
            steps {
echo "This is Development branch"            }
        }
    }
}