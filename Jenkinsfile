pipeline{
  
  agent any

stages {

   stage("build"){
     steps{
        sh 'npm install'
        sh 'ng build --prod'
     }
   }

}

stages {

   stage("test"){
     steps{
       sh './jenkins/scripts/test.sh'
     }
   }

}

stages {

   stage("deploy"){
     steps{
       sh './jenkins/scripts/deliver.sh'
       input message: 'Finished using the web site? (Click "Proceed" to continue)'
       sh './jenkins/scripts/kill.sh'
     }
   }
   
}


}
