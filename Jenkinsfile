pipeline {
  agent any
  stages {
    stage('unit') {
      steps {
        sh 'mvn clean test'
        sh 'mvn clean test'
      }
    }
    stage('integration') {
      steps {
        sh 'echo integration test'
      }
    }
    stage('ui test') {
      steps {
        build(job: 'SmokeUiTest', propagate: true, wait: true)
      }
    }
  }
}