Container for storing app secrets

##Usage

* To add secrets, run with Docker, mounting to a host directory
** docker run -v ~/hostvol:/mnt/hostvol -name add-secret shinymayhem/secrets
** / # cp /mnt/hostvol/mysql-pass /saved-secrets
** / # exit
** docker commit add-secret private/repo/mysql_secrets
** docker push private/repo/mysql_secrets
* To access secrets, create a container with a volume from the container based on the image
** docker run -name mysql-secrets private/repo/mysql_secrets
** docker run -name mysql --volume-from mysql-secrets shinymayhem/mysql

