pipeline {
  agent {
    docker { image 'node:10-alpine' }
  }
  stages {
    stage('Install') {
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
      steps {
        sh 'ng run-script test'
      }
    }

    stage('Build') {
      steps {
        sh 'npm run-script build'
      }
    }

    stage('finish') {
      steps {
        mail(subject: 'Pushed to dj-website', body: 'You pushed to dj-website.', to: 'dieter.jordens.website@gmail.com', from: 'dieter.jordens.website@gmail.com')
      }
    }

  }
}
