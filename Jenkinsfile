pipeline{
    agent any
    stages{
        stage('git checkout'){
            steps{
                sh 'git repository url'
            }
        }
        stage('maven build'){
            steps{
                sh 'maven command'
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
