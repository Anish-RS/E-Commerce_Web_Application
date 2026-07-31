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
        
    }
}
