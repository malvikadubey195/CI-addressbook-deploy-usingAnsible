pipeline {
    agent any
    
    tools
    {
       maven "mvn"
    }
     
    stages {
      stage('checkout') {
           steps {
             
                git branch: 'master', url: 'https://github.com/ashishdubey195/CI-addressbook-deploy-usingAnsible.git'
             
          }
        }
        
        
         stage('Execute Maven') {
           steps {
             
                sh 'mvn package'             
          }
        }
        stage('Ansible Deploy') {
             
            steps {
                 
             
               
               sh "ansible-playbook main.yml -i inventories/dev/hosts"

               
            
            }
        }
    }
}
