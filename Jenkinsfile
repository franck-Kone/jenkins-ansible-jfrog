pipeline{
    agent{label "master-node"}
       environment {
        SSH_KEY = credentials('master-id')  // Replace with your credential ID
    }

    stages{
        stage("Create workspace in master node"){
              steps{
                  sh "mkdir /var/lib/jenkins && mkdir /var/lib/jenkins/workspace"
              }
        }
        stage("Copy files to ansible-dev") {
            steps{
                sh "cp -r /var/lib/jenkins/workspace/ansible-config/* ~/ansible-dev/playbooks"
            }
        }
        stage("ping nodes") {
            steps{
                sh "cd ~/ansible-dev && ansible all -m ping"
            }
        }
        stage("Run playbook") {
            steps{
                sh "cd ~/ansible-dev && ansible-playbook ~/ansible-dev/plabooks/play5.yml"
            }
        }
    }
}
