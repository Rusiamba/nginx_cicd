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
          echo "====== run docker-compose ======"
          sh 'ls'
          sh 'sudo usermod -a -G docker jenkins' 
          //sh 'docker run dockerfile -d -t .' 
        }
      }
    }
}
