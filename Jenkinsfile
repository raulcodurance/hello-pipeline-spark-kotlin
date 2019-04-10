pipeline {
    agent any

    stages {
        stage('Gradle') {
            steps {
                sh './gradlew --version'
            }
        }

        stage('Test') {
                    steps {
                        sh './gradlew test'
                    }
                }
    }
}