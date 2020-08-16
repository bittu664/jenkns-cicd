 
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
                kubernetesDeploy kubeconfigId: 'my-k8', configs: 'deployment.yaml', enableConfigSubstitution: true  // REPLACE kubeconfigId
             }
        }
      }
    }

  }

}
