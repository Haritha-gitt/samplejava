pipeline {
//made some change
    agent any
    stages{
        stage('Checkout'){
            steps{
                git "https://github.com/Haritha-gitt/samplejava.git"
            }
        }
        stage('Build') {
            steps {
                    bat 'start /bjavac HelloWorld.java'
            }
        }
        stage('Test'){
            steps {
                // Run tests using a testing framework (e.g., JUnit)
                bat 'start /b java org.junit.runner.JUnitCore HelloWorldTest'
            }
        }
        stage('Dockerize') {
            steps {
                bat 'start /b docker build -t newimage .'
            }
        }
        stage('push image to dockerhub'){
            steps{
                   withCredentials([string(credentialsId: 'dockerhubvar', variable: 'dockerhubvar')]){
                        bat 'start /b docker login -u harithabondalapati -p ${dockerhubvar}'
                   }
                   bat 'start /b docker push newimage'
            }
        }
    }
}
