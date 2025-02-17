pipeline {
  agent any
  stages {
    stage('Check Maven version') {
      steps {
        sh 'echo print maven version'
        sh 'mvn -version'
      }
    }

    stage('Build') {
      steps {
        sh 'mvn clean package -DskipTests=true'
        archiveArtifacts 'target/hello-demo-*.jar'
      }
    }

    stage('Unit test') {
      steps {
        sh 'mvn test'
      }
    }

  }
  tools {
    maven 'M398'
  }
}