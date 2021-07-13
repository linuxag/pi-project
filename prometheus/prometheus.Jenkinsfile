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
                   mkdir -p /opt/docker/prometheus /opt/docker/pormetheus/conf
                   cp prometheus/etc-prometheus.yml /opt/docker/proemtheus/conf/prometheus.yml
                   chmod -R 777 /opt/docker/prometheus/
                   '''
               }
        
        }
        stage('start-dockercompose')
        {
            
            steps{
                   sh '''
                   cd prometheus
                   docker-compose -f prometheus-compose.yml up -d
                   '''
               }
        
        }
    }
}
