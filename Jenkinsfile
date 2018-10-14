pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
                sh 'mvn clean package'
            }
            
        }
        stage ('Run docker container'){
            steps {
                sh "docker build . -t tomcatwebapp:${env.BUILD_ID}"
                 }
        }
    }
}  
  
