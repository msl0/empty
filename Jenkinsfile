pipeline {
  agent {
    node {
      label 'node01'
    }

  }
  stages {
    stage('Script') {
      input {
        message 'choose environment'
        parameters {
          choice(choices: ['dev', 'prod', 'staging'], name: 'environment_value')
        }
      }
      post {
        always {
          echo '========always========'
        }

        success {
          echo '========A executed successfully========'
        }

        failure {
          echo '========A execution failed========'
        }

      }
      steps {
        echo '========executing B========'
        echo "Environment: ${environment_value}"
      }
    }

  }
  post {
    always {
      echo '========always========'
    }

    success {
      echo '========pipeline executed successfully ========'
    }

    failure {
      echo '========pipeline execution failed========'
    }

  }
  options {
    skipDefaultCheckout()
  }
}