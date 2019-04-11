pipeline {
   agent any



   stages {

   // init stage install servless npm awscli
   // config
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
              sh './gradlew deploy'
           }
      }
   }
}