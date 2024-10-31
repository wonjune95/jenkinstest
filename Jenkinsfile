pipeline {
  agent any
  stages {
    stage('Clone Git Repository') {
      steps {
        git branch: 'main', url: 'https://github.com/wonjune95/jenkinstest.git'
      }
    }
    stage('Deploy Docker Image on Master') {
      environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False'
        ANSIBLE_PRIVATE_KEY_FILE = '/var/lib/jenkins/.ssh/ansible_key'
      }
      steps {
        sh '''
        ansible-playbook -i /etc/ansible/hosts /var/lib/jenkins/workspace/wonjune/playbook.yml
        '''
      }
    }
  }
}
