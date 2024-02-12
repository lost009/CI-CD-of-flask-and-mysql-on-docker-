pipeline {
    agent { label "DOCKER_COMPOSE"}  
  
    stages {
      
        stage("code") { 
            steps {  
              git url: "https://github.com/lost009/flask-and-mysql-on-docker- , branch: "master"
            }
        }
        stage("build Test") {
            steps { 
                sh "sudo docker build -t flask . "
            }
        }
        stage("scan image") { 
            steps { 
              sh "trivy scan flask  "
            }
        }
        stage("deploy") {
          steps{
            sh "sudo docker-compose down && sudo docker-compose up -d "
          }
        }
      
    }
}

    


