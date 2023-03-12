pipeline {
    agent any
    stages {
        stage ('gitcheckout') {
            steps {
                sh 'git clone https://github.com/Ram8319/maven-project.git'
            }
        }
        stage ('maven build') {
           steps {
               sh 'mvn clean package'
           } 
        }
    }
}
