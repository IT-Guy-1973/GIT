pipeline { 
    agent any

    stages { 
        stage('Hello1') {
            steps {
                sh 'echo Hello'
            }
        }
        stage('Run Ansible job') {
            steps {
                sh '''
                export ANSIBLE_HOST_KEY_CHECKING=False ;  ansible-playbook -i inventory-cicd.yml site.yml -u ansible -b  --vault-password-file=~/.pass  ;
                '''
            }
        }
        stage(Hello2) {
            steps{
                sh 'echo This is stage 3'
            }
        }
    }
}
