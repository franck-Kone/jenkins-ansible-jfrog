pipeline{
    agent{label "master-node"}
       environment {
        SSH_KEY = credentials('master-id')  // Replace with your credential ID
    }

    stages{
        stage("Create kefky file"){
              steps{
                  sh "echo 'that is it'"
              }
        }
        stage("Copy files from github to master-node") {
            steps{
                sh "scp -r /var/lib/jenkins/workspace/ansible-config/* ec2-user@35.168.13.238:/home/ec2-user/franckFile"
            }
        }
    }
}
