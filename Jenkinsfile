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
                sh 'docker build -t myjenkinsimg .'
                sh 'docker tag myjenkinsimg sai16845/myjenimg'
                withDockerRegistry(credentialsId: 'dockerhub_id', url: '') {
                sh 'docker push sai16845/myjenimg'}
            }
        }
        
    }
}
