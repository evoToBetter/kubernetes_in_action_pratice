openssl genrsa -out https.key 2048
openssl req -new -x509 -key https.key -out https.cert -days 365 -subj /CN=www.kubia.example.com

k exec -it fortune-https -c web-server -- curl -k -v https://localhost:443 
k exec -it fortune-https -c web-server -- ls -l /etc/nginx/certs/