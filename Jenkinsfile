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
          sh 'cd \nginx_cicd'
          sh 'docker-compose up --build -d'
        }
      }
    }
}
