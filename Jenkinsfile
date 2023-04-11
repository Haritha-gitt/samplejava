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
                bat 'start/b java org.junit.runner.JUnitCore HelloWorldTest'
            }
        }
        stage('Dockerize') {
            steps {
                bat 'start/d docker build -t newimage .'
            }
        } 
    }
}
