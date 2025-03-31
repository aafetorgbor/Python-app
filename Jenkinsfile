pipeline {
  agent any
  stages {
    stage('for main branch') {
      when {
        branch 'main'
      }
      steps {
        echo 'main branch'
      }
    }
    stage('for qa branch') {
      when {
        branch 'qa'
      }
      steps {
        echo 'qa branch'
      }
    }
   stage('for dev branch') {
      when {
        branch 'dev'
      }
      steps {
        echo 'dev branch'
      }
    }
    stage('for pull request') {
      when {
        changeRequest()
      }
      steps {
        sh 'pytest -v'
      }
    }
  }
}
