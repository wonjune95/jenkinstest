pipeline {
  agent any
  stages {
    stage('Run Ansible on Master') {
      environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False'
        ANSIBLE_PRIVATE_KEY_FILE = '/home/user1/.ssh/ansible_key'
      }
      steps {
        sh '''
        ansible-playbook -i /etc/ansible/hosts /var/lib/jenkins/workspace/wonjune/playbook.yml
        '''
      }
    }
  }
}
