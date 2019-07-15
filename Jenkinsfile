pipeline {
  agent {
    node {
      label 'jenkins-slave-1'
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
    stage('Run Application Tests') {
      steps {
        sh '''docker-compose down
docker-compose build flask-app
docker-compose run flask-app pytest -v
docker-compose down
'''
      }
    }
  }
}