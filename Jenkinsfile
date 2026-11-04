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
                
                sh '''
                  whoami
                  echo "JAVA_HOME=${JAVA_HOME:-unset}"
                  java -version
                  javac -version
                  mvn -version
                  mvn clean package -DskipTests=true
                '''
            }
        }
        stage ('Unit Test') {
            steps {
                script {
                    for(int i = 0; i < 60; i++){
                        echo "${i+1}"
                        sleep 1
                    }
                }
                sh 'mvn test'
            }
        }
    }
}
