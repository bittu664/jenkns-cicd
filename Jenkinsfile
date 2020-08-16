 
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
                kubernetesDeploy kubeconfigId: 'kubeconfig2-k88', configs: 'deployment.yaml', enableConfigSubstitution: true  // REPLACE kubeconfigId
             }
        }
      }
    }
