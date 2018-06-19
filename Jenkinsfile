pipeline {
  agent any

    environment {
      PATH='${PATH}:/opt/apache-maven-3.5.3/bin'
    }

    stages {
      stage('Validate'){
        steps {
          sh 'mvn verify'
        }
      }

      stage('Compile'){
        steps{
          sh 'mvn compile'
        }
      }

      stage('Package'){
        steps{
          sh 'mvn package'
        }
      }

      stage('List all'){
        steps{
          sh 'tree'
        }
      }

    }

}
