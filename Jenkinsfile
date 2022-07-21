pipeline
{
    agent any
    stages
    {
        stage('Git')
        {
            steps
            {
                git 'https://github.com/ianmiell/simple-dockerfile.git'
            }
        }
        stage('BUilding image')
        {
            steps
            {
                sh 'docker build -t myjenkinsimg1 .'
                sh 'docker tag myjenkinsimg1 sai16845/myjenimg1'
                withDockerRegistry(credentialsId: 'dockerhub_id', url: '') {
                sh 'docker push sai16845/myjenimg'}
            }
        }
        
    }
}
