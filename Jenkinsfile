pipeline {
  agent any
  stages {
    stage('git') {
      agent any
      steps {
        git 'https://github.com/josetob/test'
      }
    }

    stage('ansible') {
      steps {
        ansiblePlaybook(playbook: 'apache.yml', become: true, becomeUser: 'root', disableHostKeyChecking: true, dynamicInventory: true, credentialsId: 'root', inventory: 'dev.inv')
      }
    }

  }
}