pipeline {
    agent any 
    stages {
        stage('Clone Repository & Clean') { 
            steps {
               sh "rm -rf jenkins-maven"
                sh "git clone https://github.com/javaexpresschannel/jenkins-maven.git"
                sh "mvn clean -f jenkins-maven"
            }
        }
        stage('Test') { 
            steps {
                sh "mvn test -f jenkins-maven "
            }
        }

        stage('deploy') { 
            steps {
                sh "mvn package -f jenkins-maven"
            }
        }
}

