pipeline {
    agent any 
    stages {

        stage('Login') { 
            steps {
                script
                    {
                
                        sh 'aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 070614107691.dkr.ecr.us-east-1.amazonaws.com'
                    }
                
            }
        }
        
        stage('Build') { 
            steps {
                script
                    {
                
                        sh 'docker build -t testapp .'
                    }
                
            }
        }
        
        stage('Tag') { 
            steps {
                script
                    {
                
                        sh 'docker tag testapp:latest 070614107691.dkr.ecr.us-east-1.amazonaws.com/testapp:latest'
                    }
                
            }
        }
        
        stage('Deploy_To_Ecr') { 
            steps {
                script
                    {
                
                        sh 'docker push 070614107691.dkr.ecr.us-east-1.amazonaws.com/testapp:latest'
                    }
                
            }
        }
            
        
    }
        
}