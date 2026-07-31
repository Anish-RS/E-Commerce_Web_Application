pipeline{
    agent any

    tools{
        nodejs 'Node20'
    }

    stages{

        stage('checkout'){
            steps{
                echo 'checking the branch'
                checkout scm
            }
        }
        stage('install depandies'){
            steps{
                dir('Cart'){
                    sh 'npm install'
                }
                dir('Product'){
                    sh 'npm install'
                }
                dir('User'){
                    sh 'npm install'
                }
                dir('front-end'){
                    sh 'npm install'
                }
            }
        }

        stage('SonarQube analysis') {
            steps {
                script {
                    def scannerHome = tool 'sonarqube'; // must match the name of an actual scanner installation directory on your Jenkins build agent
                     withSonarQubeEnv('mysonaqube') { 
                        sh "${scannerHome}/bin/sonar-scanner"
                    }
                }
            }
        }

        stage("Quality Gate") {
            steps {
              timeout(time: 1, unit: 'MINUTES') {
                waitForQualityGate abortPipeline: true
                  
                }
            }
        }
    }
}
