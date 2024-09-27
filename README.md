# ST_Assignment

## Self-signing Certificate
- To generate the tls.key: 
```
openssl genrsa -out tls.key 2048
```
- To generate the tls.crt:
```
openssl req -new -x509 -key tls.key -out tls.crt -days 365 \
-subj "/C=US/ST=State/L=City/O=Organization/OU=Unit/CN=localhost"
```
- Base64 Encode the tls.crt and tls.key and insert in templates/secret.yaml
```
cat tls.crt | base64
cat tls.key | base64
```
