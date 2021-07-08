def workspace
node
{
       
    Stage('checkout')
    {
       checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/studiesm2856/SampleProject.git']]]) 
       workspace = pwd()
        
    }
    
    Stage('code anaylsis')
    {
        build job: 'code anaylsis', parameters: [string(name: 'workspace', value: workspace)]
        
    }
    stage('code compile')
    {
        build job: 'code compile', parameters: [string(name: 'workspace', value: workspace)]
    }
    stage('code unit test')
    {
        build job: 'code unit test', parameters: [string(name: 'workspace', value: workspace)]
    }
    stage('code package')
    {
        build job: 'code packag', parameters: [string(name: 'workspace', value: workspace)]
    }
    stage('code deploy')
    {
      build job: 'Code deploy'  
    }
}
