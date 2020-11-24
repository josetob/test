pipeline {
  agent any
  stages {
    stage('git') {
      agent any
      steps {
        git(url: 'https://github.com/josetob/test.git', changelog: true)
      }
    }

    stage('ansible') {
      steps {
        ansiblePlaybook(playbook: 'apache.yml', become: true, becomeUser: 'root', disableHostKeyChecking: true, dynamicInventory: true, credentialsId: 'root', inventory: 'dev.inv')
      }
    }

  }
}
