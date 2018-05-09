pipeline {
    agent any
    stages {
        stage("ansible-playbook") {
            steps {
                script {
                    sh 'make'
                    sh 'ansible-playbook -i $inventory -u vagrant -b $playbook'
                }
            }
        }  
    }
}
