pipeline {
  agent any
  stages {
    stage('compile-app') {
      steps {
        echo 'this is the first job'
        sh 'npm install'
      }
    }

    stage('test-app') {
      steps {
        echo 'this is the second job'
        sh 'npm test'
      }
    }

    stage('package-app') {
      steps {
        echo 'this is the third job'
        sh 'npm run package'
      }
    }

    stage('archive-app') {
      steps {
        archiveArtifacts '**/distribution/*.zip'
      }
    }

  }
  tools {
    nodejs 'nodejs'
  }
  post {
    always {
      echo 'this pipeline has completed...'
    }

  }
}