 
pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/bittu664/jenkns-cicd.git'
      }
    }


    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "deployment.yaml", kubeconfigId: "my-k8")
        }
      }
    }

  }

}
