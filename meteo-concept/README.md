You need:
- WiFi101 / WiFiNINA Firmware Updater to install latest version of the firmware.

- WiFiNINA library.

- Create arduino_secrets.h with something like:
/* Wifi ID / PASSWORD */
#define MY_SSID "jfc"
#define MY_PASS "APACHECON2022"
/* meteo server information */
#define SERVER "api.meteo-concept.com"
/* Change the BASE_URL to get the information you need */
// #define BASE_URI "/api/location/city"
#define BASE_URI "/api/forecast/nextHours"
#define TOKEN "hex_toke"
#define LOC_INSEE "91457"

- USe minicom to test the output is something like:
+++
Attempting to connect to WPA SSID: MOVISTAR_E290
You're connected to the networkSSID: MOVISTAR_E290
BSSID: 34:57:60:BF:E2:91
signal strength (RSSI):-32
Encryption Type:4

IP Address: 192.168.1.152
192.168.1.152
MAC address: 9C:9C:1F:C0:99:34
SSID: MOVISTAR_E290
BSSID: 34:57:60:BF:E2:91
signal strength (RSSI):-35
Encryption Type:4

                                                                                
Starting connection to server...                                                
Connected ...                                                                   
GET /api/forecast/nextHours?token=cc7e5233ecbf496c8b0fd283ba2c1af026da1f2fd2d111
Host: api.meteo-concept.com                                                     
User-Agent: LED Map Client                                                      
Connection: close                                                               
                                                                                
Getting data                                                                    
received:                                                                       
HTTP/1.1 200 OK                                                                 
Server: nginx/1.18.0                                                            
Date: Sun, 18 Aug 2024 08:03:57 GMT                                             
Content-Type: application/json                                                  
Transfer-Encoding: chunked                                                      
Connection: close                                                               
Cache-Control: private, must-revalidate                                         
X-API-Calls: 1                                                                  
X-API-Limit: 400                                                                
pragma: no-cache                                                                
expires: -1                                                                     
X-Frame-Options: sameorigin                                                     
                                                                                
5a5                                                                             
{"city":{"insee":"91457","cp":91290,"name":"La Norville","latitude":48.5814,"lo0
HTTP/1.1 200 OK                                                                 
state: NONE                                                                     
Server: nginx/1.18.0                                                            
state: HEADER *Server: nginx/1.18.0*                                            
Date: Sun, 18 Aug 2024 08:03:57 GMT                                             
state: HEADER *Date: Sun, 18 Aug 2024 08:03:57 GMT*                             
Content-Type: application/json                                                  
state: HEADER *Content-Type: application/json*                                  
Transfer-Encoding: chunked                                                      
state: HEADER *Transfer-Encoding: chunked*                                      
Connection: close                                                               
state: HEADER *Connection: close*                                               
Cache-Control: private, must-revalidate                                         
state: HEADER *Cache-Control: private, must-revalidate*                         
X-API-Calls: 1                                                                  
state: HEADER *X-API-Calls: 1*                                                  
X-API-Limit: 400                                                                
state: HEADER *X-API-Limit: 400*                                                
pragma: no-cache                                                                
state: HEADER *pragma: no-cache*                                                
expires: -1                                                                     
state: HEADER *expires: -1*                                                     
X-Frame-Options: sameorigin                                                     
state: HEADER *X-Frame-Options: sameorigin*                                     
                                                                                
state: HEADER **                                                                
5a5                                                                             
state: CHUNK                                                                    
state: CHUNK: 1445                                                              
Done remaining data:                                                            
{"city":{"insee":"91457","cp":91290,"name":"La Norville","latitude":48.5814,"lo0
received:                                                                       
24-08-18T21:00:00+0200","temp2m":19,"rh2m":59,"wind10m":12,"gust10m":33,"dirwin}
0                                                                               
                                                                                
                                                                                
24-08-18T21:00:00+0200","temp2m":19,"rh2m":59,"wind10m":12,"gust10m":33,"dirwin}
state: DATA                                                                     
DATA:                                                                           
24-08-18T21:00:00+0200","temp2m":19,"rh2m":59,"wind10m":12,"gust10m":33,"dirwin}
0                                                                               
state: CHUNK                                                                    
state: CHUNK: 0                                                                 
                                                                                
Done!                                                                           
JSON                                                                            
{"city":{"insee":"91457","cp":91290,"name":"La Norville","latitude":48.5814,"lon
gitude":2.2657,"altitude":85},"update":"2024-08-18T11:20:03+02:00","forecast":[{
"insee":"91457","cp":91290,"latitude":48.5814,"longitude":2.2657,"datetime":"202
4-08-18T12:00:00+0200","temp2m":20,"rh2m":67,"wind10m":15,"gust10m":37,"dirwind1
0m":311,"rr10":0,"rr1":0,"probarain":10,"weather":3,"probafrost":0,"probafog":0,
"probawind70":0,"probawind100":0,"tsoil1":19,"tsoil2":18,"gustx":37,"iso0":3740}
,{"insee":"91457","cp":91290,"latitude":48.5814,"longitude":2.2657,"datetime":"2
024-08-18T15:00:00+0200","temp2m":22,"rh2m":48,"wind10m":13,"gust10m":35,"dirwin
d10m":313,"rr10":0,"rr1":0,"probarain":0,"weather":3,"probafrost":0,"probafog":0
...
+++
