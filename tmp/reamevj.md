docker build -t rules-svn .

docker run -it -d -p 80:80 -p 3960:3960 --name=rules-svn rules-svn

docker exec -t rules-svn htpasswd -b /etc/subversion/passwd user user

#run the svn locally
http://192.168.99.100/svn/


svn info svn://192.168.99.100:3960


docker exec -it svn /bin/ash


docker rmi $(docker images -f “dangling=true” -q)