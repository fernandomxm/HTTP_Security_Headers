**Configuração Microsoft IIS:**

X-Content-Type-Options: nosniff <br>
X-XSS-Protection: 1; mode=block <br>
X-Frame-Options: SAMEORIGIN <br>
Strict-Transport-Security: max-age=31536000; includeSubDomains; preload <br>
Cross-Origin-Embedder-Policy: require-corp <br>
Cross-Origin-Resource-Policy: same-origin <br>
Cross-Origin-Opener-Policy: same-origin <br>
Referrer-Policy: no-referrer-when-downgrade <br>
Content-Security-Policy: default-src 'self'; script-src 'self'; style-src 'self'; img-src *; frame-src 'self'; <br>

**Configuração Apache(httpd .conf):**
OBS: Lembre-se de habilitar o módulo de headers no servidor: a2enmod headers

Header set Content-Security-Policy "style-src 'self'; img-src 'self' blob: data: *; frame-src 'self' data:;" <br>
Header set Strict-Transport-Security "max-age=31536000; includeSubDomains; preload" <br>
Header set X-Content-Type-Options "nosniff" <br>
Header set X-XSS-Protection "1; mode=block" <br>
Header set X-Frame-Options "SAMEORIGIN" <br>
Header set Referrer-Policy "no-referrer-when-downgrade" <br>

CORS(Cross Origin Resource Sharing)

Header set Access-Control-Allow-Origin "URL_Aplicação" <br>
Header set Access-Control-Allow-Headers "Origin, Accept, Access-Control-Allow-Headers, X-Requested-With, Content-Type, Access-Control-Request-Method, Access-Control-Request-Headers, Authorization, X-Auth-Token" <br>
Header set Access-Control-Allow-Methods "GET, POST, HEAD, OPTIONS, PUT, DELETE" <br>
Header set Access-Control-Max-Age "86400" <br>
Header set Access-Control-Allow-Credentials "true" <br>
