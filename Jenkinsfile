pipeline {
    agent any

    stages {
        stage('ci') {
            steps {
               sh '/opt/maven38/bin/mvn clean package'
               sh 'mv target/sparkjava-hello-world-1.0.war target/sparkjava-hello-world-$BUILD_NUMBER.war'
               sh 'aws s3 cp target/sparkjava-hello-world-$BUILD_NUMBER.war s3://jav-cicd-application/'
            }
        }
    }
}



