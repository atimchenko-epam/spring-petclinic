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
          sh 'pwd'
        }
      }
      stage('Docker') {
        // agent {
        //   docker {
        //     image 'openjdk:8'
        //     reuseNode true
        //     args '-v /var/lib/jenkins/workspace/Pet-testing/target:/opt -p 8080:8080 java -jar /opt/spring-petclinic-2.0.0.BUILD-SNAPSHOT.jar'
        //   }
        // }
        steps {
            sh "docker run -d -v /var/lib/jenkins/workspace/Pet-testing/target:/opt -p 8080:8080 openjdk:8 java -jar /opt/spring-petclinic-2.0.0.BUILD-SNAPSHOT.jar"
        }
      }
    }
}
