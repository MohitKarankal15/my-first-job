pipeline {
  agent any
  environment {
      APP_NAME = 'demo'
  }
  stages {
      stage('Build') {
          environment {
              BUILD_MODE = 'production'
          }
          steps {
             sh 'echo $APP_NAME $BUILD_MODE'
          }
      }
  }
}  
