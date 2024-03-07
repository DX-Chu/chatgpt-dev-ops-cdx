docker container cp Nginx:/etc/nginx/nginx.conf E:\Code\chatGPT\dev-ops\nginx\conf
docker container cp Nginx:/etc/nginx/conf.d/default.conf E:\Code\chatGPT\dev-ops\nginx\\conf\conf.d
docker container cp Nginx:/usr/share/nginx/html/index.html E:\Code\chatGPT\dev-ops\nginx\html

docker run\
--name Nginx \
-p 80:80 \
-v /E:/Code/chatGPT/dev-ops/nginx/logs:/var/log/nginx\
-v /E:/Code/chatGPT/dev-ops/nginx/html:/usr/share/nginx/html \
-v /E:/Code/chatGPT/dev-ops/nginx/conf/nginx.conf:/etc/nginx/nginx.conf \
-v /E:/Code/chatGPT/dev-ops/nginx/conf/conf.d:/etc/nginx/conf.d \
-v /E:/Code/chatGPT/dev-ops/nginx/ssl:/etc/nginx/ssl/ \
--privileged=true -d --restart=always nginx

docker run -d --name Nginx -p 80:80 -v E:/Code/chatGPT/dev-ops/nginx/logs:/var/log/nginx -v E:/Code/chatGPT/dev-ops/nginx/html:/usr/share/nginx/html -v E:/Code/chatGPT/dev-ops/nginx/conf/nginx.conf:/etc/nginx/nginx.conf -v E:/Code/chatGPT/dev-ops/nginx/conf/conf.d/default.conf:/etc/nginx/conf.d/default.conf -v E:/Code/chatGPT/dev-ops/nginx/ssl:/etc/nginx/ssl/ --privileged=true -d --restart=always nginx

docker run -d --name Nginx -p 80:80 -v E:/Code/chatGPT/dev-ops/nginx/logs:/var/log/nginx -v E:/Code/chatGPT/dev-ops/nginx/html:/usr/share/nginx/html -v E:/Code/chatGPT/dev-ops/nginx/conf/nginx.conf:/etc/nginx/nginx.conf -v E:/Code/chatGPT/dev-ops/nginx/conf/conf.d:/etc/nginx/conf.d -v E:/Code/chatGPT/dev-ops/nginx/ssl:/etc/nginx/ssl/ --privileged=true -d --restart=always nginx
