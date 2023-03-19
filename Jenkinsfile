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

    stage('tomcat deploy') {
      steps {
        sh 'scp /home/ubuntu/workspace/maven-project_master/webapp/target/webapp.war 172.31.3.101:/opt/tomcat/webapps'
      }
    }

  }
}