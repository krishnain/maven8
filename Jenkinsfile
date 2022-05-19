node('built-in') 
{
    stage('ContinuousDownload') 
    {
         git 'https://github.com/intelliqittrainings/maven.git'
    }
    stage('ContinuousBuild') 
    {
         sh 'mvn package'
    }
    stage('ContinuousDeployment')
    {
deploy adapters: [tomcat9(credentialsId: 'f4a8fd35-49f8-40fb-853d-f55a9ab1d552', path: '', url: 'http://172.31.27.136:8080')], contextPath: 'testapp', war: '**/*.war'
    }
    stage('ContinuousTesting')
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline1/testing.jar'
        
    }
    stage('ContinuousDelivery')
    {
        
        deploy adapters: [tomcat9(credentialsId: 'f4a8fd35-49f8-40fb-853d-f55a9ab1d552', path: '', url: 'http://172.31.28.209:8080')], contextPath: 'prodapp', war: '**/*.war'
    }
    
    
    
    
    
    
    
    

    
    
    
}
