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

    stage('maven build') {
      steps {
        sh 'mvn clean package'
      }
    }

    stage('sonar checks') {
      steps {
        withSonarQubeEnv(installationName: 'sonar', credentialsId: 'sonar-token', envOnly: true) {
          sh 'mvn sonar:sonar'
        }

      }
    }

    stage('tomcat deploy') {
      steps {
        sh 'scp /home/ubuntu/workspace/maven-project_master/webapp/target/webapp.war 172.31.41.105:/opt/tomcat/webapps'
      }
    }

  }
}