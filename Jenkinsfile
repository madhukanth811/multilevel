pipeline
{
    agent any
    stages
    {
     stage('CONTINOUS DOWNLOAD slave')
     {
         steps
         {
             git 'https://github.com/intelliqittrainings/maven.git'
         }
     }
     stage('CONTINOUS BUILD slave')
     {
         steps
         {
             sh 'mvn package'
         }
     }
    
   }
 }

