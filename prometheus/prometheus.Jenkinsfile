def git_url = 'https://github.com/newbielinux1/pi-project.git'
def git_branch = 'main'

pipeline
{
    agent
    {
        label 'worker1'
    }

    stages
    {
        stage('env-setup')
        {
            
            steps{
                   sh '''
                   pwd
                   mkdir -p /opt/docker/prometheus /opt/docker/prometheus/conf
                   cp prometheus/etc-prometheus.yml /opt/docker/prometheus/conf/prometheus.yml
                   chmod -R 777 /opt/docker/prometheus/
                   '''
               }
        
        }
        stage('start-dockercompose')
        {
            
            steps{
                   sh '''
                   pwd
                   cd prometheus
                   whereis docker-compose
                   echo $PATH
                   /usr/bin/docker-compose -f prometheus-compose.yml down | exit 0
                   /usr/bin/docker-compose -f prometheus-compose.yml up -d
                   '''
               }
        
        }
    }
}
