pipeline {
    agent{
        label "Master"
    }
    options {
        timestamps()
    }
    stages{
        stage("Chekcout"){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '217f477c-ae18-4d4c-bf08-de299616156b', url: 'git@github.com:apulijala/simple-pipeline-practice-jenkinsfile.git']]])
            }
            
        }

        stage("Build") {
            parallel {
                stage("Test 1"){
                    steps{
                        echo "Running Test One"
                    }
                }
                stage("Test 2"){
                    steps{
                        echo "Running Test Two"
                    }
                }
                stage("Test 3"){
                    steps{
                        echo "Running Test Three"
                        python3 *test.py
                    }
                }
            }
        }
    }
    
} 
