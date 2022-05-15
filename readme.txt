Чтобы потом не забыть опять, и не вспоминать.
По факту это 3 виртуалки. 2 - контейнера и третий управляющий- nginx.
В конфиге третьего прописать всё что в файле. Образы докеры собрать, запустить. Посылать запросы на локалку(с портом 80-штатн
нгинкс, он сам репортит на другие 2 машины.

curl -XGET http://127.0.0.1:80/v1/current/city?q=Moscow -H 'Own-Auth-UserName: Oleg'

docker build -t server1 -f dockerfile1 .
docker build -t server2 -f dockerfile2 .

docker run -it --name container_1 -p 0.0.0.0:5001:8000 server1
docker run -it --name container_2 -p 0.0.0.0:5002:8000 server2


sudo service nginx restart
nginx -s reload
sudo rm -rf /etc/nginx/.nginx.conf.swp
sudo vi /etc/nginx/nginx.conf

