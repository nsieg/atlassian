~~~~
cd /home
~~~~
~~~~
docker volume create --name=ssl_certificates
~~~~
~~~~
mkdir Letsencrypt
curl -o /Letsencrypt/docker-compose.yml https://raw.githubusercontent.com/blacklabelops/atlassian/master/Letsencrypt/docker-compose.yml
cd Letsencrypt
~~~~
~~~~
docker-compose run --rm \
    -p 443:443 \
    -e LETSENCRYPT_EMAIL=nils.siegfried@quodera.com \
    -e LETSENCRYPT_DOMAIN=jira.quodera.com \
    -e LETSENCRYPT_DOMAIN2=confluence.quodera.com \
    letsencrypt install
~~~~
