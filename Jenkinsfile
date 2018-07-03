pipeline {
  agent any

    environment {
      PATH = "/opt/apache-maven-3.5.3/bin:$PATH"
      MAVEN_OPTS = "-Xmx1024m"
    }

    stages {
      stage('Install'){
        steps {
          sh 'mvn install'
        }
      }
      stage('Check if docker is running'){
        steps {
          sh 'DOCKER_CONTAINER=`docker ps -aq --filter=name=pet_clinic`'
        }
      }
      stage('Stop docker if running'){
        when {
          expression { ${DOCKER_CONTAINER} != "" }
        }
        steps {
          sh 'echo "Hello"'
        }
      }
      // stage('Docker') {
      //
      //   steps {
      //       sh "docker run -d -v /var/lib/jenkins/workspace/Pet-testing/target:/opt -p 8080:8080 --name pet_clinic openjdk:8 java -jar /opt/spring-petclinic-2.0.0.BUILD-SNAPSHOT.jar"
      //   }
      // }
    }
}
