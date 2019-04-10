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
       stage('ShadowJar') {
           steps {
              sh './gradlew shadowJar'
           }
       }
       stage('Deploy') {
           steps {
              sh 'cd build/libs java -jar sparkkotlin-all-1.0-SNAPSHOT.jar'
           }
      }
   }
}