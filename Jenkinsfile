pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                git 'https://github.com/curlingharrison/java-rest-api-calculator-1.git'
                sh './mvnw clean compile'
            }
        }
        stage('Test') {
            steps {
                sh './mvnw test'
            }

            post {
                always {
                    junit '/var/jenkins_home/workspace/calculator_api/target/surefire-reports/TEST-*.xml'
                }
            }
        }
    }
}