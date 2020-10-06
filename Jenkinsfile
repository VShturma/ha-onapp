pipeline {
    agent {label 'docker-slave-ansible'}
    stages {
        stage('Compile') {
            steps {
                ansiblePlaybook(
   		            playbook: 'playbook.yml',
   		            vaultCredentialsId: 'ansible-password',
   		            inventoryContent: '[cp1]\n10.76.0.211\n[cp2]\n10.76.0.212\n[cp3]\n10.76.0.213'
   )
            }
        }
    }
}
