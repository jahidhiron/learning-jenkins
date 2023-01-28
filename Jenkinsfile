pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/jahidhiron/learning-jenkins', branch: 'dev')
      }
    }

    stage('logs') {
      parallel {
        stage('logs') {
          steps {
            sh 'ls -la'
          }
        }

        stage('front-end-test') {
          steps {
            sh 'cd curriculum-front && npm i && npm run test:unit'
          }
        }

      }
    }

  }
}