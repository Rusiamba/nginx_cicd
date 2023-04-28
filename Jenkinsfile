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
          sh 'sudo chown -R jenkins:jenkins jobs'
          sh '/usr/bin/docker-compose up --build -d'
        }
      }
    }
}
