pipeline {
  agent any

  tools {
    
  }
  environment {
    NEW_VERSION = '1.1.0'
    SERVER_CREDENTIALS = credentials('my-git-playfield')
  }
  stages {
    
    stage("build") {
      steps {
        echo 'build the application'
        echo "building version ${NEW_VERSION}"
      }
    }

    stage("test") {
      when {
        expression {
          BRANCH_NAME == 'dev' || BRANCH_NAME == 'main'
        }
      }
      steps {
        echo 'testing the application'
      }
    }

    stage("deploy") {

      steps {
        echo 'deploying the application'
        echo "${SERVER_CREDENTIALS}"
      }
    }

  }
  post {
    always {
       // 
       echo "always print"
    }
    success {
      //
      echo "build success"
    }
    failure {
      //
      echo "build failure"
    }
  }
}