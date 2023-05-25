pipeline
{
    agent any
    stages
    {
     stage('CONTINOUS DOWNLOAD')
     {
         steps
         {
             git 'https://github.com/intelliqittrainings/maven.git'
         }
     }
     stage('CONTINOUS BUILD')
     {
         steps
         {
             sh 'mvn package'
         }
     }
     stage('CONTINOUS DEPLOYMENT')
     {
         steps
         {
             deploy adapters: [tomcat9(credentialsId: '2679f672-cf04-4c01-8265-bf657e86db6b', path: '', url: 'http://172.31.4.248:8080')], contextPath: 'testapp', war: '**/*.war'
         }
     }
     stage('CONTINOUS TESTING')
     {
         steps
         {
            git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
           sh 'java -jar /var/lib/jenkins/workspace/scriptedpipeline1/testing.jar'
         }
     }
     stage('CONTINOUS DELIVERY')
     {
         steps
         {
             deploy adapters: [tomcat9(credentialsId: '2679f672-cf04-4c01-8265-bf657e86db6b', path: '', url: 'http://172.31.14.23:8080')], contextPath: 'prodapp', war: '**/*.war'
         }
     }
     
    }
}
