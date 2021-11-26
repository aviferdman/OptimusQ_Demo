pipeline {
   agent {label 'Test'}
   stages {
      stage("Docker build") {
         steps {
            sh "docker build -t amitbaranes/dotnet-demo-sela:${env.BUILD_ID} ."
         }
      }
      stage("Login to docker hub") {
         steps {
           sh "docker login --username=${env.DOCKERHUB_USER_NAME} --password=${env.DOCKERHUB_PASSWORD}"
         }
      }
      stage("Docker push") {
         steps {
           sh "docker push  amitbaranes/dotnet-demo-sela:${env.BUILD_ID}"
         }
      }
      stage("Docker run ") {
         steps {
           sh " docker run -d -p 8080:80 --name myapp amitbaranes/dotnet-demo-sela:${env.BUILD_ID}"
         }
      }
   } 
    post {
        always {
            cleanWs deleteDirs: true, notFailBuild: true
        }
    }
}