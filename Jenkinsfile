pipeline {
  agent any
  stages {
    stage("Git checkout"){
        git credentialsId: 'GITHUB', url: 'https://github.com/ArinUsole/example-playbook.git'
    }
    stage("Check ssh key"){
        secret_check=true
    }
    stage("Run playbook"){
        if (secret_check){
            sh 'ansible-playbook site.yml -i inventory/prod.yml'
        }
        else{
            echo 'no more keys'
        }
    }
  }
}
