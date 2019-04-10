pipeline {
   agent any

   stages {
       stage('Gradle') {
           steps {
               sh './gradlew --version'
           }
       }
       stage('FatJar') {
            steps {
               sh './gradlew fatJar'
            }
       }
      stage('Run') {
           steps {
              sh 'cd build/libs java -jar sparkkotlin-all-1.0-SNAPSHOT.jar'
           }
      }
   }
}