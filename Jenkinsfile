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
  }
}