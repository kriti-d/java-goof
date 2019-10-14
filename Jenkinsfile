pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'maven install'
      }
    }
    stage('snyk') {
      steps {
        snykSecurity(snykInstallation: 'SNYKv2Test', monitorProjectOnBuild: true, failOnIssues: true, targetFile: 'results.html')
      }
    }
  }
}