@Library('sharedlibrary')_
pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload-Master')
        {
            steps
            {
                script
                {
                     cicd.newGit("https://github.com/intelliqittrainings/maven.git")
                }
            }
        }
        stage('ContinuousBuild_Master')
        {
            steps
            {
                script
                {
                     cicd.newMaven()
                }
            }
        }
        stage('ContinuousDeploymnt_Master')
        {
            steps
            {
                script
                {
                     cicd.newDeploy("http://172.31.27.136:8080","testapp")
                }
            }
        }
        stage('ContinuousTesting_Master')
        {
            steps
            {
                script
                {
                     cicd.newGit("https://github.com/intelliqittrainings/FunctionalTesting.git")
                     cicd.runSelenium("Pipelinewithlibraries")
                    
                }
            }
        }
        stage('ContinuousDelivery_Master')
        {
            steps
            {
                script
                {
                     cicd.newDeploy("http://172.31.28.209:8080","prodapp")
                }
            }
        }
        
        
        
        
        
        
        
        
        
        
        
   
    }
}
