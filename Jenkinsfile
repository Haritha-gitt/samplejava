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
                    bat 'start /b javac HelloWorld.java'
            }
        }
        stage('Test'){
            steps {
                // Run tests using a testing framework (e.g., JUnit)
                bat 'start /b java org.junit.runner.JUnitCore HelloWorldTest'
            }
        }
        stage('build docker image') {
            steps {
                bat 'start /b docker build -t newimage .'
            }
        }
        stage('push image to dockerhub'){
            steps{
                      withCredentials([string(credentialsId: 'dockerhubid', variable: 'dockerhubvar')]) {
                          bat 'start /b docker login -u ${dockerhubcred} -p ${Hari@2306}'
                          bat 'start /b docker push dockerhubcred/newimage'
                      }
            }
        }
    }
}
