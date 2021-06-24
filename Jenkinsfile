node('master') 
{
    stage('ContinuousDownload_Main')
    {
        git 'https://github.com/intelliqittrainings/maven.git'             
    }
    stage('ContinuousBuild_Main')
    {
        sh 'mvn package'
    }
    stage('ContinuousDeployment_Main')
    {
    sh 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.30.223:/var/lib/tomcat9/webapps/testapp.war'

    }

    stage('ContinuousTesting_Main')
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline/testing.jar'
    }
}
