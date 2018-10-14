pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage ('Run docker container'){
            steps {
                sh 'docker build . -t tomcatwebapp:${env.BUILD_ID}'
            }
        }
    }
}  
  
