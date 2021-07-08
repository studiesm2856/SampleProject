def workspace
pipeline
{
    agent any 
    stages{ 
    stage("checkout")
    {
    steps{ 
  checkout([$class: "GitSCM", branches: [[name: "*/master"]], extensions: [], userRemoteConfigs: [[url: "https://github.com/studiesm2856/SampleProject.git"]]])
Script { 
       workspace = pwd()
        }
    }  
    }
    }
    stage('code anaylsis')
    {
     steps{
        build job: 'code anaylsis', parameters: [string(name: 'workspace', value: workspace)]
    }

    }
    stage('code compile')
    {
	steps{
        build job: 'code compile', parameters: [string(name: 'workspace', value: workspace)]
	}
    }

    stage('code unit test')
    {
    steps{
        build job: 'code unit test', parameters: [string(name: 'workspace', value: workspace)]
    }
    }
    stage('code package')
    {
     steps{
        build job: 'code packag', parameters: [string(name: 'workspace', value: workspace)]
       }
    }
    stage('code deploy')
    {
     steps{

      build job: 'Code deploy'  
    }

}
}
}
