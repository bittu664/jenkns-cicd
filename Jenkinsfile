 
pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/bittu664/jenkns-cicd.git'
      }
    }
   
   
  

   stage("Deploy to Staging"){
      
            steps {
                kubernetesDeploy credentialsType: 'KubeConfig',kubeconfigId: [path: '/home/ubuntu/.kube/config'], configs: 'deployment.yaml', enableConfigSubstitution: true  // REPLACE kubeconfigId
             }
        }
      }
    
