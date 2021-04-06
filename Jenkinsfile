pipeline {
    agent any
    tools {
        maven "maven3.6.6"
    }
    stages {
        stage('checkout&build') {
            steps {
                git 'https://github.com/jenkinsdemorepo/mavenproject'
                sh "mvn package"
            }
        }
        stage('manual approval') {
            steps {
                input "Do you want to deploy to staging environment ?"
            }
        }
        stage('deploy') {
            steps {
                sh "cp target/JenkinsWar.war /var/lib/tomcat9/webapps/"
            }
        }
    }
}
