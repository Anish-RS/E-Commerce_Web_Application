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
                dir('E-Commerce_Web_Application/Cart'){
                    sh 'npm install'
                }
                dir('E-Commerce_Web_Application/Product'){
                    sh 'npm install'
                }
                dir('E-Commerce_Web_Application/User'){
                    sh 'npm install'
                }
                dir('E-Commerce_Web_Application/front-end'){
                    sh 'npm install'
                }
            }
        }
        
    }
}
