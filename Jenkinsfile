pipeline{

agent any

environment{
  DEPLOY_TO = 'Production'
}


stages{
    stage('Build'){
        steps{
              echo 'This is a Build stage'
        }
       
    }
     stage('Test'){
       steps{
         echo 'This is a Test stage'
       }
     }

     stage('Deploy'){
      steps{
        echo 'This is a Deply stage'
      }
     }
}
post{
    always{
      echo 'This will always run'
    }
    success{
      echo 'This will run when the pipeline is success'
    }
   failure{
     echo 'This will run when the pipeline is failed'
   }
  
  }

}