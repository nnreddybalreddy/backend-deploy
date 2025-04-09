pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
        ansiColor('xterm')
    }
    parameters {
        string(name: 'appVersion', defaultValue: '1.0.0', description: 'What is the application version?')
    }
  
    environment{
        defappVersion =''
        nexusUrl ='nexus.narendra.shop:8081'
        region ="us-east-1"
        account_id ="905418111046"

    }    

    stages {
        stage('print the version'){
            steps{
                script{
                    echo "Application version: ${params.appVersion}"
                }
            }
        }

    }

    post { 
        always { 
            echo 'I will always say Hello again!'
            deleteDir()
        }
        success { 
            echo 'I will run when pipeline is success'
        }
        failure { 
            echo 'I will run when pipeline is failure'
        }
    }
}

