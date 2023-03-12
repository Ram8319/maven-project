pipeline{
    agent any
    stages{
        stage('git checkout'){
            steps{
                sh 'git clone https://github.com/Ram8319/maven-project.git'
            }
        }
        stage('maven build'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('sonar checks'){
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-pip-token') {
                        sh 'mvn sonar:sonar'
                      }
                    }
                }
            }
        }
}
