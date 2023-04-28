properties([disableConcurrentBuilds()])

pipeline {
    agent any
    options {
      buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10'))
      timestamps()
    }
    stages {
      stage("Run Docker Compose") {
        agent {
          docker {
            image 'nginx'
          }  
        }  
        steps {
          echo "====== run docker-compose ======"
          dir ('/nginx_cicd') {
            sh 'docker-compose build'  
            sh 'docker-compose up -d'   
          }
        }
      }
    }
}
