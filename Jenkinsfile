pipeline {
    agent any
    stages{
        stage("deploy to stage/prod env") {
            steps {
		    withCredentials([file(credentialsId: 'git-crypt', variable: 'git_crypt')]) {
                    sh 'git-crypt unlock "$git_crypt"'
                    sh "chmod 600 ssh_keys/*"
                    sh "ansible-playbook -i $inventory --extra-vars 'BUILD_ID=$BUILD_ID' $playbook"
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
