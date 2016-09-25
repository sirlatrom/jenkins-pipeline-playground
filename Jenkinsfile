node {
  stage 'Checkout'
  checkout scm
  stage 'Clean'
  sh './mvnw clean'
  stage 'Test'
  sh './mvnw test'
  stage 'Package'
  sh './mvnw -DskipTests package'
}
