pipeline {
    agent {
        docker {
            image  '352708296901.dkr.ecr.eu-north-1.amazonaws.com/danishain-jenkins-ex1:latest'
            args  '--user root -v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages {

           stage('Build') {
               steps {
                   sh 'docker build -t webapp:$IMAGE_TAG .'
               }
           }
           stage('Run') {
               steps {
                   sh 'docker run -p 8501:8501 webapp'
               }
           }
       }
   }