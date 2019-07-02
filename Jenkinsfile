pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Echo Some Text') {
      steps {
        sh 'echo "jenkins job ocean blue"'
      }
    }
    stage('Run App') {
      steps {
        dir(path: 'flask-app') {
          sh 'docker-compose up -d --build'
        }

      }
    }
  }
}