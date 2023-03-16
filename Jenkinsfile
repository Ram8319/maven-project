pipeline {
  agent {
    node {
      label 'slave'
    }

  }
  stages {
    stage('git checkout') {
      steps {
        git(url: 'https://github.com/Ram8319/maven-project.git', branch: 'master', credentialsId: 'Git-token')
      }
    }

  }
}