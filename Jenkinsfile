pipeline{
    agent any
    stages{
        stage ('SCM Checkout'){
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'git', url: 'https://github.com/shekar55/tomcat-ansible.git']])
            }
        }
        stage('Execute Ansible'){
            steps{
                ansiblePlaybook credentialsId: 'ubuntu11', disableHostKeyChecking: true, installation: 'ansible', inventory: 'hosts', playbook: 'tomcat-setup.yml'
                }
        }
            
    }    
}
