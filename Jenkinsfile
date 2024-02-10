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
              dir('Compute-Linux')  {
                git changelog: false, credentialsId: 'bigcokeadmin', poll: false, url: 'https://github.com/bigcokeadmin/linux-support.git'
              }
                sh '''
                pwd ;
                ls ;
                export ANSIBLE_HOST_KEY_CHECKING=False ;  ansible-playbook -i Compute-Linux/inventory-cicd.yml site.yml -u hettin -b  ;
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
