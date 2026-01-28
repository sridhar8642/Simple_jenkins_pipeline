pipeline {
    agent {
        docker {
            image 'ubuntu:22.04'
            args '-u root'
        }
    }

    stages {

        stage('Install Java') {
            steps {
                sh '''
                  apt-get update
                  apt-get install -y openjdk-17-jdk git
                  java -version
                '''
            }
        }

        stage('Checkout Code') {
            steps {
                git 'https://github.com/YOUR_USERNAME/hello-jenkins-docker-agent.git'
            }
        }

        stage('Compile Java') {
            steps {
                sh 'javac HelloWorld.java'
            }
        }

        stage('Run Java Program') {
            steps {
                sh 'java HelloWorld'
            }
        }
    }
}
