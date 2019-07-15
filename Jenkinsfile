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
        sh '''cd flask-app
docker-compose down
docker-compose build flask-app
docker-compose run flask-app pytest -v --junit-xml=/var/opt/junit-report/report.xml
docker-compose down
'''
      }
    }
    stage('Archive JUnit-formatted test results') {
      steps {
        sh '''sudo rm -rf flask-app/junit-report
'''
      }
    }
  }
}