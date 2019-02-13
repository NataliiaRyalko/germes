pipeline {
  agent any
  stages {
    stage('unit test') {
      steps {
        withEnv(overrides: ["PATH+EXTRA=/usr/local/bin"]) {
          sh 'mvn clean test'
        }

      }
    }
    stage('integration test') {
      steps {
        sh 'echo \'Integration test is running\''
      }
    }
    stage('UI tests') {
      steps {
        build(job: 'Smoke_UI_Test', propagate: true, wait: true)
      }
    }
  }
}
