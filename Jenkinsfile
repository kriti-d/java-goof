pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        sh 'java -version'
        sh 'mvn -v'
      }
    }
    stage('build') {
      steps {
        sh 'mvn clean install'
      }
    }
    stage('snyk') {
      steps {
        snykSecurity(snykInstallation: 'SNYKv2Test', monitorProjectOnBuild: true, failOnIssues: true, targetFile: 'results.html', snykTokenId: '1c6964f4-b2b2-4366-9335-ed1f8eb14d26', organisation: 'Demo Org', projectName: 'java-goo', severity: 'low')
      }
    }
  }
  tools {
    maven 'maven-3.6.0'
  }
}