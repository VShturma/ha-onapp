pipeline {
    agent {label 'docker-slave-ansible'}
    stages {
        stage('Configure OS') {
            steps {
                ansiblePlaybook(
                            playbook: '2-configureOS.yml',
                            vaultCredentialsId: 'ansible-password',
                            inventoryContent: '[master]\n10.76.0.211\n[slave1]\n10.76.0.212\n[slave2]\n10.76.0.213')
            }
        }
        stage('Install OnApp') {
            steps {
                ansiblePlaybook(
                            playbook: '3-installOnApp.yml',
                            vaultCredentialsId: 'ansible-password',
                            inventoryContent: '[master]\n10.76.0.211\n[slave1]\n10.76.0.212\n[slave2]\n10.76.0.213')
            }
        }
        stage('Configure Nodes') {
            steps {
                ansiblePlaybook(
                            playbook: '4-configureNodes.yml',
                            vaultCredentialsId: 'ansible-password',
                            inventoryContent: '[master]\n10.76.0.211\n[slave1]\n10.76.0.212\n[slave2]\n10.76.0.213')
            }
        }
    }
}

