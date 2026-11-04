pipeline {
    agent any
    tools { 
        maven "M310"
    }
    stages {
        stage('Echo Version') {
            steps {
                sh 'echo Print Maven Version'
                sh 'mvn -version'
            }
        }
        stage('Build') {
            steps {
                //git 'https://github.com/Amon3422/jenkins-hello-world.git'
                
                sh 'mvn clean package -DskipTests=true'
            }
        }
        stage ('Unit Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
