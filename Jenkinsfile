pipeline {

    agent any

    stages{

        stage('Git checkout'){ 
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/jndansi/aws-ansible.git']]])
            }
        }
        
        stage('Change Directory') {
            steps {
                dir('/etc/ansible') {
                    // sh 'sleep 65'
                    sh 'ansible-playbook -i /opt/ansible/inventory/aws_ec2.yaml /etc/ansible/playbook.yaml'
                }
            }
        }
            
    }

}
