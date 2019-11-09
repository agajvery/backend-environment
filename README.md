```bash
## Follow the link and install Docker
https://docs.docker.com/docker-for-mac/install/

## Follow the link and install docker-compose
https://docs.docker.com/compose/install/

# Get repo 
wget https://github.com/agajvery/backend-environment/archive/master.zip
unzip master.zip

mv backend-environment-master {your_project_name}
cd {your_project_name}


# You may need to create a `.env` from the `.env.example` :
cp .env.example .env

# Build nginx/app/mysql images
docker-compose build

# Spin up APP (defaults to binding to port 80)
docker-compose up -d

#Create composer autoload
docker-compose exec app composer dump-autoload

# Add hosts
sudo -s

export `cat .env | grep BASE_DOMAIN`  # for example domain my-site.test in file .env

echo "127.0.0.1 \
$BASE_DOMAIN
" >> /etc/hosts

exit 

Open your host in browser by default my-site.test 

```