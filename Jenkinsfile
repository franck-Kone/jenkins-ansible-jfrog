pipeline{
    agent{label "master-node"}
       environment {
        SSH_KEY = credentials('master-id')  // Replace with your credential ID
           HOME_DIR = "/var/lib/jenkins"
    }

    stages{
        // stage("Create workspace in master node"){
        //       steps{
                
        //           sh "sudo mkdir /var/lib/jenkins && sudo mkdir /var/lib/jenkins/workspace"
        //       }
        // }
        stage("Copy files to ansible-dev") {
            steps{
                sh "pwd"
                sh "mv /home/ec2-user/workspace/ansible-config/* ~/ansible-dev/playbooks"
            }
        }
        stage("ping nodes") {
            steps{
                sh "cd ~/ansible-dev && ansible all -m ping"
            }
        }
        stage("Run playbook") {
            steps{
                sh "cd ~/ansible-dev && ansible-playbook ~/ansible-dev/plabooks/ansible-config/play5.yml"
            }
        }
    }
}
