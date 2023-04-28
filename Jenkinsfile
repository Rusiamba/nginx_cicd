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
          git branch: 'main',
          url: 'https://github.com/Rusiamba/nginx_cicd.git'
          sh 'pwd'
          //echo "====== run docker-compose ======"
          dir('nginx_cicd') {
            sh 'ls'
            sh 'docker run --name my-custom-nginx-container -d custom-nginx'
          }
        }
      }
    }
}
