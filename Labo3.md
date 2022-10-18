# Labo 3

## Curl:

1. `osboxes@osboxes:~$ curl -s icanhazip.com `
 <br> output: `193.191.158.22`

2. oefening 2:
    1. HTML pagina van de site hmpg.net
    2. `osboxes@osboxes:~/Documents$ curl -s -o test.html https://hmpg.net`
    3. Neen, de image wordt niet weergegeven bij het bestand test.html
    4. De file wordt gwn overschreven is net hetzelfde als we >> zouden gebruiken

3. Oefening 3:
    1. <!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
    <html><head>
    <title>302 Found</title>
    </head><body>
    <h1>Found</h1>
    <p>The document has moved <a href="https://hmpg.net/">here</a>.</p>
    <hr>
    <address>Apache Server at hmpg.net Port 8080</address>
    </body></html> 
    <br>
    2. `osboxes@osboxes:~/Documents$ curl -I -s hmpg.net/` <br>
    Status = 302 found
    <br> Met  https://hmpg.net/: Satus = 200
    3. `osboxes@osboxes:~/Documents$ curl -L -s hmpg.net/`
    

4. Oefening 4:
    1. Wordt gedownload
    2. `osboxes@osboxes:~/Documents$ curl -s -L -o test.md http://ftp.belnet.be/debian/README`
    3. `osboxes@osboxes:~/Documents$ curl -s -L -o test.md http://ftp.belnet.be/debian/README --user "anonymous:test"` <br>username: anonymous en password: test


5. Oefening 5:
    1. De uitvoer is in json
    2. `osboxes@osboxes:~/Documents$ curl -s -L  https://en.wikipedia.org/api/rest_v1/page/random/summary | jq . `
    3. -s staat voor silent

6. 