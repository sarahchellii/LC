pipeline {
    agent any
    
    stages{
    
    
        stage('Pull'){
            steps {
                echo 'Pulling..';
                  git branch: 'master',
                  url : 'https://github.com/sarahchellii/LC.git';
            }
        }
        
            
        stage('Build'){
             steps { 
                    script{
                    sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml --ask-become-pass"
                    }
                }
             }
        
        
           stage('docker')
        {
             steps {
                    script{
             sh "ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml"
                          }
                   }
          }         
        
        
        
        
        
 }
 }
