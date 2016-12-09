node {
  stage 'Checkout'
  checkout scm
  stage 'Clean'
  sh './mvnw clean'
  stage 'Test'
  sh './mvnw test'
  junit 'target/test-reports/*.xml'
  stage 'Package'
  sh './mvnw -DskipTests package'
  archiveArtifacts artifacts: 'target/*.jar', fingerprint: true, onlyIfSuccessful: true
}
