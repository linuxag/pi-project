def git_url = 'https://github.com/newbielinux1/pi-project.git'
def git_branch = 'main'

pipeline
{
    agent
    {
        label 'piserver'
    }

    stages
    {
        stage('env-setup')
        {
            
            steps{
                   sh '''
                   mkdir -p /opt/docker/grafana
                   chmod 777 /opt/docker/grafana/
                   '''
               }
        
        }
        stage('start-dockercompose')
        {
            
            steps{
                   sh '''
                   cd grafana
                   docker-compose -f grafana-compose.yml up -d
                   '''
               }
        
        }
    }
}
