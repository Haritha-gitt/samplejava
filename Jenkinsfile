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
                bat 'start /b docker build -t Haritha-gitt/newimage .'
            }
        }
        /*stage('push image to dockerhub'){
            steps{
                     withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'dockerhubcred', passwordVariable: 'DOCKER_PASSWORD')]) {
          sh 'docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD'
          sh 'docker push your-docker-image'
            }
        }*/
    }
}
