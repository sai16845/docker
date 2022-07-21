pipeline
{
    agent any
    environment
    {
        dockerImage=''
        registry='sai16845/pyimage'
        registryCredentials='dockerhub_id'
    }
    stages
    {
        stage('Checkout')
        {
            steps
            {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://bitbucket.org/ananthkannan/mypythonrepo/']]])
            }
        }
        stage('Build Docker img')
        {
            steps
            {
                script
                {
                    dockerImage=docker.build registry
                    
                }
            }
        }
        stage('Uploading image')
        {
            steps
            {
                script
                {
                    docker.withRegistry( '',registryCredentials ){
                        dockerImage.push()
                    }
                    
                    
                }
            }
        }
    }
}
    
