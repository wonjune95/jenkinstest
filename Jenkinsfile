pipeline {
  agent any
  environment {
    WORKSPACE = "${env.WORKSPACE}"
  }
  stages {
    stage('git scm update') {
      steps {
        git url: 'https://github.com/wonjune95/jenkinstest.git', branch: 'main'
      }
    }
    stage('docker build and push') {
      steps {
        sh '''
        ansible-playbook -e workspace=${WORKSPACE} /path/to/docker_build_push.yml
        '''
      }
    }
    stage('deploy and service') {
      steps {
        sh '''
        ansible-playbook -e workspace=${WORKSPACE} /path/to/k8s_deploy.yml
        '''
      }
    }
  }
}
