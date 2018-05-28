pipeline {
    agent any
    stages{
        stage("run playbook to deploy project and check it") {
            steps {
		            withCredentials([file(credentialsId: 'git-crypt', variable: 'git_crypt')]) {
                    sh 'git-crypt unlock "$git_crypt"'
                    sh "sudo chmod 600 ssh_keys/*"
                    sh "ansible-playbook -i $inventory --extra-vars 'BUILD_ID=${env.BUILD_ID}' -u vagrant -b $playbook"
                }
            }
        }
    }
    post {
      always {
        sh 'git-crypt lock'
      }
    }
}
