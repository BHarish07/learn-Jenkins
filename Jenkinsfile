pipeline{

//agent any
agent{
    label 'AGENT-1'
}

environment{
  DEPLOY_TO = 'Production'
}

parameters{
    choice(name: 'action', choicea: ['Apply', 'Destroy'], description: 'Pick Something')

}

stages{
    stage('Build'){
        steps{
              echo 'This is a Build stage'
        }
       
    }
     stage('Test'){
      when{
          expression{
            params.action == 'Apply'
          }
      }
       steps{
         echo 'This is a Test stage'
       }
     }

     stage('Deploy'){
      when{
          expression{
            params.action == 'Apply'
          }
      }
      input{
          message "Should we continue?"
          ok "Yes, we should."
          submitter "Harish"
      }
      steps{
        echo 'This is a Deploy stage'
      }
     }
     
     stage('Destroy'){
      when{
          expression{
            params.action == 'Destroy'
          }
      }
      steps{
        echo 'This is a Destroy stage'
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