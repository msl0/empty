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
                choice(choices: ['dev', 'prod', 'staging'], name: 'environment_value')
              }
            }
            steps{
                echo "========executing B========"
                echo "Environment: ${environment_value}"
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
