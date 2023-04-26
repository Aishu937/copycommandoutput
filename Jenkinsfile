pipeline {
    agent {label 'masternodes'}
    
    stages {
      stage('parallel Task A & C') {
          parallel {
              stage('Print Job Name & Node Name') {
                  steps {
                      sh 'echo "The ${JOB_NAME} run on ${NODE_NAME}"'
                       echo "the global email is ${var_email}"
                      
                    }
                  
               }
              stage ("create file"){
                   steps{
                      sh 'ls -la > command.output'
                       echo "command output is redirected to the command.output file"
                    }
                }    
            }
        }    
        stage ("copy file to jenkins"){
            steps{
              sh "ssh jenkins@192.168.1.27 mkdir -p aishwarya"
                echo "folder of your name is created on jenkins"
                 sh "/usr/bin/scp /jenkins-node/workspace/Aishwarya/copycommandoutput/command.output jenkins@192.168.1.27:/home/jenkins/aishwarya"

            }
        }
    }
}
