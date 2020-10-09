pipeline {
    agent {label 'docker-slave-ansible'}
    stages {
        stage('install') {
            steps {
                ansiblePlaybook(
   		            playbook: '2-configureOS.yml',
   		            vaultCredentialsId: 'ansible-password',
   		            inventoryContent: '[master]\n10.76.0.211\n[slave1]\n10.76.0.212\n[slave2]\n10.76.0.213'
   )
                ansiblePlaybook(
                            playbook: '3-installOnApp.yml',
                            vaultCredentialsId: 'ansible-password',
                            inventoryContent: '[master]\n10.76.0.211\n[slave1]\n10.76.0.212\n[slave2]\n10.76.0.213'
   )
                ansiblePlaybook(
                            playbook: '4-configureSSH.yml',
                            vaultCredentialsId: 'ansible-password',
                            inventoryContent: '[master]\n10.76.0.211\n[slave1]\n10.76.0.212\n[slave2]\n10.76.0.213'
   )

            }
        }
    }
}
