pipeline {
   agent any
   environment {
      IMAGE_NAME = "view_count:latest"
   }
   stages {
      stage("checkout code"){
         steps{
            echo "pulling latest code from github..."
            git branch: 'main', url:'https://github.com/vinod73570/view_count.git'
         }
      }
      stage("build docker images"){
         staps {
            echo "building docker images..."
            sh "docker build -t ${IMAGE_NAME} ."
         }
      }
      stage("create container using docker-compose up") {
         steps {
            echo " creating containers "
            sh "docker compose down || true "
            sh "docker compose up -d "
         }
      }
   }
}

    

