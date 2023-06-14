pipeline { 
    agent any

    stages { 
        stage('Hello1') {
            steps {
                sh 'echo Hello'
            }
        }
        stage(sleep) {
            steps {
                sh 'sleep 60'
            }
        }
        stage(Hello2) {
            steps{
                sh 'echo This is stage 3'
            }
        }
    }
}
