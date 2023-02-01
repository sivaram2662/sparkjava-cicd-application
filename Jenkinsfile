pipeline {
    agent any

    stages {
        stage('CD') {
            steps {
               sh '/opt/maven38/bin/mvn clean package'
               sh 'mv target/sparkjava-hello-world-1.0.war target/sparkjava-hello-world-$BUILD_NUMBER.war'
               sh 'aws s3 cp target/sparkjava-hello-world-$BUILD_NUMBER.war s3://jav-cicd-application/'
            }
        }
        //  stage('Docker') {
        //     steps {
        //        sh 
        //     }
        // }
         stage('CD') {
            steps {
               sh 'aws s3 cp s3://jav-cicd-application/sparkjava-hello-world-$PKG.war .'
               sh 'scp -r sparkjava-hello-world-$PKG.war root@172.31.25.214:/opt/tomcat/webapps'
            }
        }
    }
}



