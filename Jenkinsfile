pipeline {
  agent any
  stages {
    stage('git scm update') {                   # git으로 처리하겠다.
      steps {
        git url: 'https://github.com/wonjune95/jenkinstest.git', branch: 'main'
      }
    }
    stage('docker build and push') {            # docker로 처리하겠다.
      steps {
        sh '''
        sudo docker build -t wonjune95/keduit:puple .
        sudo docker push wonjune95/keduit:puple
        '''
      }
    }
    stage('deploy and service') {               # kubernetes로 처리하겠다.
      steps {
        sh '''
        sudo kubectl apply -f deploy_lb.yml
        '''
      }
    }
  }
}
