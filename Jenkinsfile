pipeline {
//made some change
    agent any
    stages{
        stage('Checkout'){
            steps{
                git "https://github.com/Haritha-gitt/javaproject.git"
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
    }
}
