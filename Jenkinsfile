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
 deploy adapters: [tomcat9(credentialsId: 'f246e795-097e-4148-9dfe-e8c76c27e948', path: '', url: 'http://172.31.30.223:8080')], contextPath: 'testapp', war: '**/*.war'

    }

    stage('ContinuousTesting_Main')
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline/testing.jar'
    }
}
