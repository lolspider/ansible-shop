pipeline {
    agent any
    stages {
        stage("ansible-playbook") {
            steps {
                script {
                    sh 'make'
                    sh 'ansible-playbook -i $inventory --extra-vars "spring_boot_version=$spring_boot_version" -u vagrant -b $playbook'
                }
            }
        }  
    }
}
