pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M398"
    }

    stages {
        stage('Check Maven version'){
            steps{
            sh "echo print maven version"
            sh "mvn -version"
            }
        }
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                // git branch: 'main', url: 'https://github.com/jithinkp11p/jenkins-hello-world.git'

                // Run Maven on a Unix agent.
                sh "mvn clean package -DskipTests=true"
            }

           
        }
        stage('Unit test'){
            steps{
            sh "mvn test"
            }
        }
    }
}
