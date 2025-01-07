pipeline {
    agent any  
    stages {
        stage ('Checkout') {
            steps {
                git branch: 'main' , 
                    url: 'https://github.com/santoshrana95/practiceansible.git' ,
                    credentialsId: 'ansible-ssh-key'
            }
        }
        stage ('Run Ansible playbook') {
            steps {
                ansiblePlaybook(
                    playbook: 'ansible.yaml',
                    extras: '-i inventory.ini --private-key /opt/jenkins/workspace/jenkins1/id_rsa.key -u ec2-user' )
            }
        }
    }
}