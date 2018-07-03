pipeline {
  agent any

    environment {
      PATH = "/opt/apache-maven-3.5.3/bin:$PATH"
      MAVEN_OPTS = "-Xmx1024m -XX:MaxPermSize=512m"
    }

    stages {
      stage('Install'){
        steps {
          sh 'mvn install'
        }
      }
      stage('LS'){
        steps {
          sh 'ls'
        }
      }
      stage('Docker') {
        agent {
          docker {
            image 'openjdk:8'
            reuseNode true
            args '-v /var/lib/jenkins/workspace/Pet-testing/target:/opt'
          }
        }
        steps {
          sh 'java -version'
        }
      }
    }
}
