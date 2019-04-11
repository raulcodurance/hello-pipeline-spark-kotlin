pipeline {
   agent any

options{

withAWS(credentials:'IDofAwsCredentials') {
sh './serverless config credentials --provider aws --key ${AWS_ACCESS_KEY_ID} --secret ${AWS_SECRET_ACCESS_KEY}
}
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