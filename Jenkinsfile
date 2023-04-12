pipeline {
  agent {
    node {
      label 'Node1'
    }

  }
  stages {
    stage('Pull Repository') {
      steps {
        git(url: 'https://github.com/spring-projects/spring-petclinic', branch: 'main')
      }
    }

    stage('Run Sonar') {
      steps {
        withSonarQubeEnv 'SonarQubeServer'
        waitForQualityGate true
      }
    }

  }
}