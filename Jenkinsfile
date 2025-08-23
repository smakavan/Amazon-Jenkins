pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git url: 'https://github.com/smakavan/Amazon-Jenkins.git', branch: 'main'
      }
    }

    stage('Build WAR') {
      steps {
        sh 'mvn clean package'
      }
    }

    stage('SonarQube Analysis') {
      steps {
        withSonarQubeEnv('SonarQube') {
  	sh 'mvn sonar:sonar'
	}
      }
    }

   stage('Deploy to Tomcat') {
      steps {
        ansiblePlaybook(
          playbook: 'ansible/deploy.yml',
          inventory: 'ansible/hosts.ini'
        )
      }
    }
  }
}
