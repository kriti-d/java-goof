pipeline {
  agent any
  tools { 
    maven 'maven-3.6.0'
  }
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
        snykSecurity(snykInstallation: 'SNYKv2Test', monitorProjectOnBuild: true, failOnIssues: true, targetFile: 'results.html')
      }
    }
  }
}
