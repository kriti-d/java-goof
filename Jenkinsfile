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
        snykSecurity(snykInstallation: 'SNYKv2Test', monitorProjectOnBuild: true, failOnIssues: true, targetFile: 'results.html', snykTokenId: '5478e634-e045-46e4-807e-59b32bc5cefe', organisation: 'Demo Org', projectName: 'java-goo', severity: 'low')
      }
    }
  }
  tools {
    maven 'maven-3.6.0'
  }
}