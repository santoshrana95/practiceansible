pipeline {
    aganet any  
    stages {
        stage ('Checkout') {
            steps {
                git branch: 'main' , 
                    url: 'https://github.com/santoshrana95/practiceansible.git'
                    credentialsId: 'ansible-ssh-key'
            }
        }
        stage ('Run Ansible playbook') {
            steps {
                ansiblePlaybook(
                    playbook: 'ansible.yaml',
                    extras: '-i inventory.ini --private-key /opt/jenkins/workspace/practiceansible/id_rsa.key -u ec2-user')
            }
        }
    }
}