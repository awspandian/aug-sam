pipeline {
    agent any

    stages {
        stage('scm') {
            steps {
                git 'https://github.com/awspandian/aug-sam.git'
            }
        }
		stage('Build') {
            steps {
                sh 'mvn clean'
				sh 'mvn install'
            }
        }
		stage('Deployment') {
            steps {
                sh 'cp -rp "/var/lib/jenkins/workspace/demo-pipeline/target/my-web.war" "/opt/apache-tomcat/webapps"'
            }
        }
    }
}
