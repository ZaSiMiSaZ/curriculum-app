pipeline {
  agent any
  stages {
    stage('Checkout Code') {
      steps {
        git(url: 'https://github.com/zasimisaz/curriculum-app', branch: 'dev')
      }
    }

    stage('Log') {
      steps {
        sh 'ls -la'
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -f curriculum-front/Dockerfile .'
      }
    }

    stage('Login Dockerhub ') {
      environment {
        DOCKERHUB_USER = 'zasimisaz'
        DOCKER_PASSWORD = 'S3cur30n3!'
      }
      steps {
        sh 'docker login -u $DOCKERHUB_USER -p $DOCKERHUB_PASSWORD'
      }
    }

  }
}