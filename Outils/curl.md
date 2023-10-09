# cURL Cheat-Sheet

| Command | Description |
|:---------|:--------|
| ```curl -h```| cURL help menu |
| ```curl google.fr```| Basic GET request |
| ```curl -s google.fr/index.html```| Download the file |
| ```curl -k https://google.com```| Skip HTTPS (SSL) certificate validation |
| ```curl google.com -v``` | Print full HTTP request/response details |
| ```curl -I https://google.com``` | Send HEAD request (only prints response headers) |
| ```curl -i https://google.com``` | Print response headers and response body |
| ```curl https://google.com -A 'Mozilla/5.0'``` | Set User-Agent header |
| ```curl -u admin:admin http://<SERVER_IP>:<PORT>/``` | Set HTTP basic authorization credentials |
| ```curl http://admin:admin@<SERVER_IP>:<PORT>/``` | Pass HTTP basic authorization credentials in the URL |
| ```curl -H 'Authorization: Basic YWRtaW46YWRtaW4=' http://<SERVER_IP>:<PORT>/``` | Set request header |
| ```curl 'http://<SERVER>:<PORT>/search.php?search=le'``` | Pass GET parameters |
| ```curl -X POST -d 'username=admin&password=admin' http://<SERVER_IP>:<PORT>/``` | Send POST request with POST data |
| ```curl -b 'PHPSESSID=<COOKIE_PHP_SESSION> http://<SERVER_IP>:<PORT>/``` | Set request cookies |
| ```curl -X POST -d '{"search":"london" }' -H 'Content-Type: application/json' http://<SERVER_IP>:<PORT>/search.php``` | Send POST request with JSON data |