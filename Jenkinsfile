properties([disableConcurrentBuilds()])

pipeline {
    agent any
    options {
      buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10'))
      timestamps()
    }
    stages {
      stage("Run Docker Compose") {
        steps {
          echo "====== run docker-compose ======"
          dir ('/var/jenkins_home/workspace/nginx_cicd@tmp'){
            sh 'docker-compose up --build -d'
          }
        }
      }
    }
}
