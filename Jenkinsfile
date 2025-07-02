pipeline {
    agent { label 'win-slave-sachin1' }
    stages {

        stage('pull scm step') {
            steps {
                git branch: 'main', url: 'https://github.com/smakavan/Amazon-Jenkins'
            }
        }
        stage('compile') {
            steps {
                bat 'mvn compile'
            }
        }

        stage('build') {
            steps {
                 bat 'mvn clean install'
            }
        }
    }
  }
