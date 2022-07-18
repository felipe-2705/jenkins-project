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
                    sh 'pwd'
                    sh 'ls -lha'
                    sh 'mvn clean test'
            }
        }
     }
    post {
       always {
          junit(
        allowEmptyResults: true,
        testResults: '*/test-reports/.xml'
      )
      }
    } 
}