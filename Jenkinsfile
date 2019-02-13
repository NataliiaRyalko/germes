pipeline {
  agent any
  stages {
    
    stage('unit test') {
      steps {
        withEnv(["PATH+EXTRA=/usr/local/bin"]) {
          sh 'mvn clean test'
        }
      }
    }

    stage('integration test') {
      steps {
        sh 'echo \'Integration test are . running\''
      }
    }

    stage('UI tests') {
      steps {
        build(job: 'smokeUiTest', propagate: true, wait: true)
      }
    }
  }
}
