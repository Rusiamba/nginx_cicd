properties([disableConcurrentBuilds()])

pipeline {
    agent {
      label 'main'
    }
    options {
      buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10'))
      timestamps()
    }
    stages {
      stage("Run Docker Compose") {
        steps {
          echo "====== run docker-compose ======"
          sh 'docker-compose up -d'
        }
      }
    }
}
