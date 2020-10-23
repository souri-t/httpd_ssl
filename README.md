# httpd_ssl

ref:https://qiita.com/tukiyo3/items/3d1634a1fa0477976f74


mkdir certs; cd certs

# 1.秘密鍵
openssl genrsa -out server.key 3072

# 2. csr
openssl req -new -key server.key -out server.csr -subj "/CN=example.com"

# 3. csrを署名したcrt
openssl x509 \
 -req \
 -in server.csr \
 -days 36500 \
 -signkey server.key > server.crt
