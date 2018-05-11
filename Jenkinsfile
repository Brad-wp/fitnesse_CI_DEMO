pipeline {
    agent any
    environment {
          def scannerHome = tool 'sonar_scanner'
    }
    // Test 1
    stages {
        stage('Build') {
            steps {
                  sh './gradlew'
            }
            
        }
        /*
        stage('Test') {
            steps {
                  sh './gradlew test'
            }
           
        }
        */
        stage('Sonarqube'){
            steps{
                withSonarQubeEnv('sonar') {
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
}
