pipeline {
  agent {
    node {
      label 'binary build'
    }

  }
  stages {
    stage('Binary build') {
      steps {
        sh 'sshpass -phyperdata1234! ssh -o StrictHostKeyChecking=no root@192.168.179.44 \'curl http://192.168.1.222:5002/hyperdataBuildApi/release20.4; exit\''
      }
    }

    stage('create image') {
      steps {
        sshPublisher(masterNodeName: 'root')
      }
    }

  }
}