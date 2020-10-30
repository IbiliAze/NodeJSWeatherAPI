pipeline {
  agent any

  triggers {
    cron('H/15 * * * *') #H-hash, min, hour, month, dow
  }

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
        git 'https://github.com/IbiliAze/Jenkins.git'
      }
    }

    stage('Build') {
      steps {
        sh '''npm init
        npm install
        node src/app.js
      }
    }
    stage('Post') {
      steps {
        archiveArtifacts artifacts: 'output.txt', followSymlinks: false
      }
    }
  }
}
