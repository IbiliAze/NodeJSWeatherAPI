pipeline {
  agent any

  stages {

    stage('Echo') {
      steps {
        echo 'hello1'
        sh '''pwd
        ls -a
        echo $USER'''
      }
    }

    stage('Pull') {
      steps {
        git 'https://github.com/IbiliAze/NodeJSWeatherAPI'
      }
    }

    stage('Build') {
      steps {
        sh '''npm install
        node src/app.js '''
      }
    }
  }
}
