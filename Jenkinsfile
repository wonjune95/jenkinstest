pipeline {
  agent any
  stages {
    stage('Run Ansible on Master') {
      steps {
        sh '''
        ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook -i /etc/ansible/hosts /var/lib/jenkins/workspace/wonjune/playbook.yml
        '''
      }
    }
  }
}
