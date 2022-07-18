pipeline {
    agent any
    tools {
        maven 'maven'
        jdk   'JAVA'
    }
    stages {
        stage('Initialize'){
            steps{
                echo "PATH = ${M2_HOME}/bin:${PATH}"
                echo "M2_HOME = opt/maven"
            }
        }
        stage('Build') {
            steps {
                dir("var/lib/jenkins/workspace/maven-test/jenkins-project/") {
                    sh 'pwd'
                    sh 'ls -lha'
                    sh 'mvn clean test'
                }
            }
        }
     }
}