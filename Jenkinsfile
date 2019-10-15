pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        sh 'java -version'
        sh 'mvn -v'
      }
    }
    stage('snyk') {
      steps {
        snykSecurity(snykInstallation: 'SNYKv2Test', monitorProjectOnBuild: true, snykTokenId: 'snyk-token', projectName: 'java-goof', severity: 'high')
      }
    }
  }
  tools {
    maven 'maven-3.6.0'
  }
}