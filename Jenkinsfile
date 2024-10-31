pipeline {
  agent any
  stages {
    stage('Run Ansible on Master') {
      steps {
        // Ansible이 마스터에 명령을 전달하는 플레이북 실행
        sh '''
        ansible-playbook -i /etc/ansible/hosts /path/to/playbook.yml
        '''
      }
    }
  }
}
