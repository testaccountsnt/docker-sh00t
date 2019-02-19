1. ### Enter into directory sh00t-with-python3-docker-image and run bulid.
cd /path/of/sh00t-with-python3-docker-image
docker build -t sh00t:latest .
### or run build with path of directory sh00t-with-python3-docker-image
docker build -t sh00t:latest /path/of/sh00t-with-python3-docker-image

2. ### Once process is completed and you return back on command prompt.
docker run -it -p 8001:8001 sh00t:latest

3. ### Open browser and run http://localhost:8001
Admin Credentials
username	:	admin
password	:	Password@123

Note :
1. After successfully accessing sh00t in browser, if you exit the command prompt. Now you want to access it again in browser with all existing data, find the container id using command
docker ps -a
Now start the container again using command
docker start f7528650649b
where f7528650649b is container id.
Now open in browser again http://localhost:8001

2. If you are not able to get internet connection inside docker container as you get error 'could not resolve hostname github.com' or similar, add google name server in your resolv.conf file
cat /etc/resolv.conf
nameserver 8.8.8.8
