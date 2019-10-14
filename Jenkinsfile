pipeline {
  agent any
  tools { 
    maven 'maven-3.6.0'
  }
  stages {
    stage('build') {
      steps {
        sh 'mvn clean install'
      }
    }
    stage('snyk') {
      steps {
        snykSecurity(snykInstallation: 'SNYKv2Test', monitorProjectOnBuild: true, failOnIssues: true, targetFile: 'results.html')
      }
    }
  }
}
