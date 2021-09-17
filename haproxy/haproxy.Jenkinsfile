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
                   cd haproxy
                   pwd
                   mkdir -p /opt/docker/haproxy
                   chmod 777 /opt/docker/haproxy/
                   cp haproxy/haproxy.cfg /opt/docker/haproxy/
                   '''
               }
        
        }
        stage('start-dockercompose')
        {
            
            steps{
                   sh '''
                   pwd
                   cd haproxy
                   docker-compose -f haproxy-compose.yml down | exit 0
                   docker-compose -f haproxy-compose.yml up -d
                   '''
               }
        
        }
    }
}
