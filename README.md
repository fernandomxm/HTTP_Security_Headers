**Configuração Microsoft IIS:**

X-Content-Type-Options: nosniff
X-XSS-Protection: 1; mode=block
X-Frame-Options: SAMEORIGIN
Strict-Transport-Security: max-age=31536000; includeSubDomains; preload
Cross-Origin-Embedder-Policy: require-corp
Cross-Origin-Resource-Policy: same-origin
Cross-Origin-Opener-Policy: same-origin
Referrer-Policy: no-referrer-when-downgrade
Content-Security-Policy: default-src 'self'; script-src 'self'; style-src 'self'; img-src *; frame-src 'self';

**Configuração Apache(httpd .conf):**
OBS: Lembre-se de habilitar o módulo de headers no servidor: a2enmod headers

Header set Content-Security-Policy "style-src 'self'; img-src 'self' blob: data: *; frame-src 'self' data:;"
Header set Strict-Transport-Security "max-age=31536000; includeSubDomains; preload"
Header set X-Content-Type-Options "nosniff"
Header set X-XSS-Protection "1; mode=block"
Header set X-Frame-Options "SAMEORIGIN"
Header set Referrer-Policy "no-referrer-when-downgrade"

CORS(Cross Origin Resource Sharing)

Header set Access-Control-Allow-Origin "URL_Aplicação"
Header set Access-Control-Allow-Headers "Origin, Accept, Access-Control-Allow-Headers, X-Requested-With, Content-Type, Access-Control-Request-Method, Access-Control-Request-Headers, Authorization, X-Auth-Token"
Header set Access-Control-Allow-Methods "GET, POST, HEAD, OPTIONS, PUT, DELETE"
Header set Access-Control-Max-Age "86400"
Header set Access-Control-Allow-Credentials "true"
