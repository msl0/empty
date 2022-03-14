pipeline{
    agent any
    options {
        skipDefaultCheckout()
    }
    stages{
        stage("Script"){
            input {
              message 'choose environment'
              parameters {
                choice choices: ['dev', 'prod', 'staging'], name: 'env'
              }
            }
            steps{
                echo "========executing B========"
                echo "Environment: ${env}"
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========A executed successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
