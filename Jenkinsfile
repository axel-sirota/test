pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        git(url: 'https://github.com/axel-sirota/jenkins-course', branch: 'main')
        sh 'mvn -f simple-app clean compile'
      }
    }

    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            sh 'mvn -f simple-app package'
          }
        }

        stage('') {
          steps {
            echo 'I am running in parallel'
          }
        }

      }
    }

    stage('Third stage') {
      steps {
        build 'Lab9'
      }
    }

  }
}