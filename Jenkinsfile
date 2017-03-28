pipeline {
  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }
    stage('Clean') {
      steps {
        sh './mvnw clean'
      }
    }
    stage('Test') {
      steps {
        sh './mvnw test'
        junit 'target/surefire-reports/*.xml'
      }
    }
    stage('Package') {
      steps {
        sh './mvnw -DskipTests package'
        archiveArtifacts artifacts: 'target/*.jar', fingerprint: true, onlyIfSuccessful: true
      }
    }
  }
}
