pipeline {
    agent any
   stages {

        stage('pull scm step') {
            steps {
                git branch: 'Dev', url: 'https://github.com/smakavan/Amazon-Jenkins'
            }
        }
        stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('build') {
            steps {
                 sh 'mvn clean install'
            }
        }
    }
  }
