pipeline{
    agent{label "master-node"}

    stages{
        stage("Create kefky file"){
              steps{
                  sh "mkdir ~/franckFile"
              }
        }
        stage("Copy files from github to master-node") {
            steps{
                sh "scp -r /var/lib/jenkins/workspace/ansible-config/* ec2-user@35.168.13.238:/home/ec2-user/franckFile"
            }
        }
    }
}
