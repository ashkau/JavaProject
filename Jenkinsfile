pipeline {
        agent none
        stages {
            stage('Non-Parallel stage') {
                agent{
                         label "master"
                     }
                steps {
                     echo 'This is a non parallel stage and will execute on master node'
                 }
                }
            stage('Parallel steps') {
                parallel{
                    stage('Test on Windows-Node node'){
                        agent{
                            label "Windows-Node"
                        }
                        steps{
                            echo "This is test on Windows-Node machine"
                        }
                    }
                    
                    stage('Test on master node'){
                        agent{
                            label "master"
                        }
                        steps{
                            echo "This is test on master machine"
                        }
                    }
                }   
                 
                }
                 
                 
}
post{
    always{
        echo "post run - will Always run"
    }
    success{
        echo "post run - will run when success"
    }
    failure{
        echo "post run - will run when failure"
    }
    unstable{
        echo "post run - will run when unstable"
    }
    changed{
        echo "post run - will run when there is any change from previous build run"
    }
}
}
