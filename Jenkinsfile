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
          sh 'sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose'
          sh 'docker-compose up --build -d'
        }
      }
    }
}
