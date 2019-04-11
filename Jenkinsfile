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

       stage('Config AWS Credentials'){
           steps{
             sh './serverless config credentials --provider aws --key ${AWS_ACCESS_KEY_ID} --secret ${AWS_SECRET_ACCESS_KEY}
           }
       }

       stage('Deploy') {
           steps {
              sh './gradlew deploy'
           }
      }
   }
}