pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK'
    }

    stages {

        stage('Checkout') {
            steps {
                git url: 'https://github.com/CyberBrain18/test2.git', branch: 'master'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Deploy') {
            steps {
                sh 'sudo cp target/MymavenWebApp.war /opt/tomcat/webapps/MymavenWebApp01.war'
            }
        }
    }

    post {
        success {
            echo "Successfully deployed MymavenWebApp01 to Tomcat on port 9090."
        }
        failure {
            echo "Pipeline failed. Check Jenkins tool names or sudo permissions."
        }
    }
}
