pipeline {
    agent any
   stages {

        stage('pull scm') {
            steps {
                git branch: 'main', url: 'https://github.com/smakavan/Amazon-Jenkins'
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
