pipeline {
   agent any

   stages {
       stage('Gradle') {
           steps {
               sh './gradlew --version'
           }
       }
       stage('Tests') {
           steps {
              sh './gradlew build'
           }
       }
       stage('FatJar') {
           steps {
              sh './gradlew fatJar'
           }
       }
       stage('Deploy') {
           steps {
              sh 'cd build/libs java -jar sparkkotlin-all-1.0-SNAPSHOT.jar'
           }
      }
   }
}