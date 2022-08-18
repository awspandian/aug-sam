pipeline {
    agent any

    stages {
        stage('SCM') {
            steps {
                git 'https://github.com/awspandian/aug-sam.git'
            }
        }
     	stage('BUILD') {
            steps {
                sh 'mvn clean'
		sh 'mvn install'
            }
        }
     	stage('DEPLOY') {
            steps {
		sh 'cp -rp "/var/lib/jenkins/workspace/pipeline/target/my-web.war" "/opt/apache-tomcat/webapps"'
            }
        }
    }
}
