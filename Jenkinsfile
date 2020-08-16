 
pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/bittu664/jenkns-cicd.git'
      }
    }
   
   stage('deploy to k8') {
      steps {
       sshagent{['ec2']} {
         sh "scp -o StrictHostKeyChecking=no deployment.yaml ubuntu@3.236.121.209:/home/ubuntu/"
         script{
            try{
              sh "ssh ubuntu@3.236.121.209 kubectl apply -f deployment.yaml"
            }catch(error){ 
                sh "ssh ubuntu@3.236.121.209 kubectl create -f deployment.yaml"
       }
         } 
      }
    }
   }
  }

   stage("Deploy to Staging"){
      
            steps {
                kubernetesDeploy kubeconfigId: 'kubeconfig2-k88', configs: 'deployment.yaml', enableConfigSubstitution: true  // REPLACE kubeconfigId
             }
        }
      }
    
