pipeline{

    agent{
        label "jenkins-slave-ssh"
    }

    stages{

        stage("Checkout Datta") {
            steps {
                echo "Checkout from SCM"
            }
        }

        stage("Build") {

           parallel {

               stage ("First Test") {
                    steps {
                        echo "Running test 1"
                    }
               }
                
                stage ("Second Test") {

                    steps {
                        echo "Running test 2"
                    }

               }

               stage ("Third Test") {
                    
                    steps {
                        sh 'python3 *test.py'
                    }
               }

           } 

        }

    }
    
    post {

        success{
            echo "========pipeline executed successfully ========"
        }
 
        failure {
            echo "========pipeline execution failed========"
        }
    }
}
