node {
  def mvnHome = tool 'M3'
  def mvn = "${mvnHome}/bin/mvn"

  stage "Checkout"
  checkout scm

  stage "Build"
  sh "${mvn} compile"

  stage "Test"
  sh "${mvn} test"

  stage "Package"
  sh "${mvn} package"
  archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
}
