pipeline {

    agent any

    stages{

        stage('Git checkout'){ 
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/jndansi/aws-ansible.git']]])
            }
        }
        
        stage('Run Ansible Playbook'){
            steps{
                sh 'sudo ansible-playbook playbook.yaml'
            }
        }
    
    
    }

}
