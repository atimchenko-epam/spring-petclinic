pipeline {
  agent any

    environment {
      PATH = "/opt/apache-maven-3.5.3/bin:$PATH"
      MAVEN_OPTS = "-Xmx1024m -XX:MaxPermSize=512m"
      DOCKER_CONTAINERS = sh 'docker inspect  -f "{{.Id}} {{.Config.Cmd}}" $(docker ps -a -q)'
    }

    stages {
      stage('Install'){
        steps {
          sh 'mvn install'
        }
      }
      // stage('Check if docker is running'){
      //   when {
      //     expression {}
      //   }
      //   steps {
      //     sh
      //   }
      // }
      // stage('Docker') {
      //
      //   steps {
      //       sh "docker run -d -v /var/lib/jenkins/workspace/Pet-testing/target:/opt -p 8080:8080 openjdk:8 java -jar /opt/spring-petclinic-2.0.0.BUILD-SNAPSHOT.jar"
      //   }
      // }
    }
}
