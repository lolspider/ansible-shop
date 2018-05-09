pipeline {
    agent any
    stages {
        stage("git") {
            steps {
                git (credentialsId: '5fbf29ca-18b1-462c-87c8-ec8f88a4788e', url: 'https://github.com/lolspider/ansible-shop.git')
            }        
        }
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
