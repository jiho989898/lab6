pipeline {
  agent any
  stages {
    stage('git scm update') {
      steps {
        git url: 'https://github.com/jiho989898/lab6.git', branch: 'main'
      }
    }
    stage('docker build and push') {
      steps {
        sh '''
        sudo docker build -t jiho9898/keduinitlab:purple .
        sudo docker push jiho9898/keduinitlab:purple
        '''
      }
    }
    stage('deploy -> master') {
      steps {
        sh '''
        sudo ansible-playbook ./play.yml
        sudo ansible-playbook ./play1.yml
        '''
      }
    }
  }
}
