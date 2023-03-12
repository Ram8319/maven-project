pipeline {
    agent any
    stages {
        stage ('gitcheckout') {
            steps {
                sh 'git clone https://github.com/Ram8319/mavenrepo.git'
            }
        }
        stage ('maven build') {
           steps {
               sh 'mvn clean package'
           } 
        }
    }
}
