pipeline {
    agent {
        docker {
            image 'ubuntu:22.04'
            args '-u root'
        }
    }

    options {
        skipDefaultCheckout(true)
    }

    stages {

        stage('Install Java & Git') {
            steps {
                sh '''
                  apt-get update
                  apt-get install -y openjdk-17-jdk git
                '''
            }
        }

        stage('Checkout Code') {
            steps {
                git url: 'https://github.com/sridhar8642/Simple_jenkins_pipeline.git',
                    branch: 'master',
                    credentialsId: 'github-creds'
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
