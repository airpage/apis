---
title: AiRPAGE OPEN API 사용법

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - php 
  - javascript
  - python

toc_footers:
  - <div class="fb-like" data-href="https://www.facebook.com/airpage.org/" data-width="100" data-layout="button_count" data-action="like" data-size="small" data-show-faces="false" data-share="false"></div>
  - <a href='http://airpage.org/'>AiRPAGE 홈</a>
  - <a href='http://airpage.org/xe/airpage_apis'>AiRPAGE 개발자 등록</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>
includes:
  - errors

search: true
---

# 소개 

'AiRPAGE OPEN API를 사용해 보세요'

이곳은 '두근두근(DKDK)', '시시콜콜(콜백나우)', '컴다운'의 OPEN API 사용법을 제공하는 사이트 입니다. 
쌈박하고 깔끔한 아이디어가 녹아든 쉽고 간편한 OPEN API와 코드들을 둘러 보세요.


# 토큰 발급 받기 

> OPEN API 사용을 위해 AiRPAGE 개발자 토큰을 발급 받으세요.


```shell

```

```php

```

```javascript

```

```python

```


> 

AiRPAGE OPEN API는 AiRPAGE 개발자 토큰을 파라메터로 입력해야 사용하실 수 있습니다.
아래 경로에서 먼저 토큰을 발급 받으세요.

[토큰얻기](http://airpage.org/xe/airpage_apis).

발급받은 토큰의 사용방법은 각 OPEN API의 설명을 참고해 주세요.

<aside class="notice">
AiRPAGE OPEN API를 사용하시려면 반드시 <code>토큰</code>을 API의 파라메터로 입력해야 합니다. 간수에 유의해 주세요.
</aside>

# 두근두근(DKDK) API 사용법 

## 친구신청 하기 


```shell

curl "http://apis.airpage.org/your-access-token/dkdkrequest/friendid"

```

```php

$get = curl_init();
curl_setopt($get, CURLOPT_URL, "http://apis.airpage.org/your-access-token/dkdkrequest/friendid");
$result = curl_exec($get);
echo $result;

```

```javascript

$.ajax({
  url : "http://apis.airpage.org/your-access-token/dkdkrequest/friendid",
  dataType : "jsonp",
  type : "GET",
  success : function(r) { console.log(JSON.stringify(r)); },
  error : function(err) { console.log(JSON.stringify(err)); }
});

```

```python

import requests 
URL = 'http://apis.airpage.org/your-access-token/dkdkrequest/friendid' 
res = requests.get(URL)

if res.status_code is not 200:
  print ("error")
else:
  print ("success")
  print (res.text)

```

> 상기의 명령은 아래와 같이 JSON 구조로 응답합니다:

```json
  {
    "result": "success"
  }
```

친구에게 친구요청을 전송합니다.

### HTTP 요청 

`GET http://apis.airpage.org/[:token]/dkdkrequest/[:friendid]`

### URL 파라메터

파라메터 | 설명
--------- | -----------
token | 부여받은 개발자 토큰값을 입력합니다. 
dkdkrequest | 'dkdkrequest'을 입력합니다. 
friendid | 친구의 아이디를 입력합니다.

<aside class="warning">
GET 형식으로 API가 호출되는 만큼 토큰의 노출에 유의하세요!
</aside>

## 두근거림 전송하기


```shell

curl "http://apis.airpage.org/your-access-token/dkdktouch"

```

```php

$get = curl_init();
curl_setopt($get, CURLOPT_URL, "http://apis.airpage.org/your-access-token/dkdktouch");
$result = curl_exec($get);
echo $result;

```

```javascript

$.ajax({
  url : "http://apis.airpage.org/your-access-token/dkdktouch",
  dataType : "jsonp",
  type : "GET",
  success : function(r) { console.log(JSON.stringify(r)); },
  error : function(err) { console.log(JSON.stringify(err)); }
});

```

```python

import requests 
URL = 'http://apis.airpage.org/your-access-token/dkdktouch?callback=abc' 
res = requests.get(URL)

if res.status_code is not 200:
  print ("error")
else:
  print ("success")
  print (res.text)


```
> 상기의 명령은 아래와 같이 JSON 구조로 응답합니다:

```json

{ 
   "result" : "success"
}

```

친구에게 두근거림을 전송합니다.

### HTTP 요청 

`GET http://apis.airpage.org/[:token]/dkdktouch`

### URL 파라메터

파라메터 | 설명
--------- | -----------
token | 부여받은 개발자 토큰값을 입력합니다. 
dkdktouch | 'dkdktouch'을 입력합니다. 



## 두근거림 전송 끝내기


```shell

curl "http://apis.airpage.org/your-access-token/dkdkup"

```

```php

$get = curl_init();
curl_setopt($get, CURLOPT_URL, "http://apis.airpage.org/your-access-token/dkdkup");
$result = curl_exec($get);
echo $result;

```

```javascript

$.ajax({
  url : "http://apis.airpage.org/your-access-token/dkdkup",
  dataType : "jsonp",
  type : "GET",
  success : function(r) { console.log(JSON.stringify(r)); },
  error : function(err) { console.log(JSON.stringify(err)); }
});

```

```python

import requests 
URL = 'http://apis.airpage.org/your-access-token/dkdkup?callback=abc' 
res = requests.get(URL)

if res.status_code is not 200:
  print ("error")
else:
  print ("success")
  print (res.text)


```
> 상기의 명령은 아래와 같이 JSON 구조로 응답합니다:

```json

{ 
   "result" : "success"
}

```

친구에게 전송하던 두근거림을 멈춥니다.

### HTTP 요청 

`GET http://apis.airpage.org/[:token]/dkdkup`

### URL 파라메터

파라메터 | 설명
--------- | -----------
token | 부여받은 개발자 토큰값을 입력합니다. 
dkdkup | 'dkdkup'을 입력합니다. 


## 주고받은 하트수 보기 


```shell

curl "http://apis.airpage.org/your-access-token/dkdkhistory/target-year"

```

```php

$get = curl_init();
curl_setopt($get, CURLOPT_URL, "http://apis.airpage.org/your-access-token/dkdkhistory/target-year");
$result = curl_exec($get);
echo $result;

```

```javascript

$.ajax({
  url : "http://apis.airpage.org/your-access-token/dkdkhistory/target-year",
  dataType : "jsonp",
  type : "GET",
  success : function(r) { console.log(JSON.stringify(r)); },
  error : function(err) { console.log(JSON.stringify(err)); }
});

```

```python

import requests 
URL = 'http://apis.airpage.org/your-access-token/dkdkhistory/target-year?callback=abc' 
res = requests.get(URL)

if res.status_code is not 200:
  print ("error")
else:
  print ("success")
  print (res.text)


```
> 상기의 명령은 아래와 같이 JSON 구조로 응답합니다:

```json

{
   "result" : "success",
   "sentdata" : [
	{
		"count":"5",
		"time":"2018-03-27 22:47:30"
	},
	{
		"count":"12",
		"time":"2018-03-28 01:04:45"
	}
   ],
   "recvdata" : [
	{
		"count":"37",
		"time":"2018-03-27 22:47:30"
	},
	{
		"count":"83",
		"time":"2018-03-28 01:04:45"
	}
   ]
}

```

친구와 주고받은 하트수와 시각을 응답합니다.

### HTTP 요청 

`GET http://apis.airpage.org/[:token]/dkdkhistory/[:year]`

### URL 파라메터

파라메터 | 설명
--------- | -----------
token | 부여받은 개발자 토큰값을 입력합니다. 
dkdkhistory | 'dkdkhistory'을 입력합니다. 
year | 확인하고픈 연도 4자리 숫자를 입력합니다. 

# 시시콜콜(콜백나우) API 사용법 

## 전화요청 하기 


```shell

curl "http://apis.airpage.org/your-access-token/neocallback/your-phone-number/kr/friendid"

```

```php

$get = curl_init();
curl_setopt($get, CURLOPT_URL, "http://apis.airpage.org/your-access-token/neocallback/your-phone-number/kr/friendid");
$result = curl_exec($get);
echo $result;

```

```javascript

$.ajax({
  url : "http://apis.airpage.org/your-access-token/neocallback/your-phone-number/kr/friendid",
  dataType : "jsonp",
  type : "GET",
  success : function(r) { console.log(JSON.stringify(r)); },
  error : function(err) { console.log(JSON.stringify(err)); }
});

```

```python

import requests 
URL = 'http://apis.airpage.org/your-access-token/neocallback/your-phone-number/kr/friendid' 
res = requests.get(URL)

if res.status_code is not 200:
  print ("error")
else:
  print ("success")
  print (res.text)

```

> 상기의 명령은 아래와 같이 JSON 구조로 응답합니다:

```json
  {
    "result": "success"
    "opname":"SRTelecom",
    "iso":"kr",
    "phone_number":"01011111111"
  }
```

친구에게 전화요청을 전송합니다.

### HTTP 요청 

`GET http://apis.airpage.org/[:token]/neocallback/[:phonenumber]/[:iso]/[:friendid]`

### URL 파라메터

파라메터 | 설명
--------- | -----------
token | 부여받은 개발자 토큰값을 입력합니다. 
neocallback | 'neocallback'을 입력합니다. 
phonenumber | 연락받을 전화번호를 입력합니다.
iso | 연락받을 전화번호의 국가 ISO값을 입력합니다.
friendid | 친구의 아이디를 입력합니다.

<aside class="warning">
GET 형식으로 API가 호출되는 만큼 토큰의 노출에 유의하세요!
</aside>

<aside class="warning">
전화요청은 30초후에 자동으로 요청이 종료 됩니다.
</aside>



## 전화요청 종료하기 


```shell

curl "http://apis.airpage.org/your-access-token/neocancel/your-phone-number/friendid"

```

```php

$get = curl_init();
curl_setopt($get, CURLOPT_URL, "http://apis.airpage.org/your-access-token/neocancel/your-phone-number/friendid");
$result = curl_exec($get);
echo $result;


/******************************************************************/
// 암호화 전송 예제

//이곳에 부여 받은 토큰 정보를 입력합니다.   
$myToken = "MYTOKENMYTOKEN";
 
//이곳에 개발자 등록당시 사용한 호스트 정보를 입력합니다.
$myHost = "airpage.org";    
 
//전화걸기 요청을 보내기 위한 방법 입니다.
//내전화번호, 내ISO코드, 전화요청 대상 전화번호, 전화요청 대상 ISO코드, 전화요청 대상에게 표시될 메시지, 요청명령
send_sisicallcall_service("01010041004","kr","01011111111","kr","조금 까다롭던 그 고객", "callback");
 
//전송한 전화걸기 요청을 취소하기 위한 방법 입니다.
//내전화번호, 내ISO코드, 전화요청 대상 전화번호, 전화요청 대상 ISO코드, 취소명령
//send_sisicallcall_service("01010041004","kr", "01011111111","kr","", "cancel");
 
class GCrypt
{   


var $sKey = "";     
             
function setKey($KEY)
{
    $this->sKey = $KEY;
}                       
                                                                             
function encrypt ($value)
{                
    $padSize = 16 - (strlen ($value) % 16) ;
    $value = $value . str_repeat (chr ($padSize), $padSize) ;
    $output = mcrypt_encrypt (MCRYPT_RIJNDAEL_128, $this->sKey, $value, MCRYPT_MODE_CBC, str_repeat(chr(0),16)) ;                
    return base64_encode ($output);
}
 
function getmillis()
{
	date_default_timezone_set("GMT+0");
        list($u_sec, $sec) = explode(' ', microtime());
        return (int) ((int) $sec * 1000 + ((float) $u_sec * 1000));
}
    

}
         
    
 
function send_sisicallcall_service($p_myphonenumber, $p_myiso, $p_phonenumber, $p_iso, $p_mymsg, $p_how)
{       
   global $myHost, $myToken;
         
   $mcrypt = new GCrypt();
   $mcrypt->setKey($myToken);
                                             
   $now = $mcrypt->getmillis();         
                             
   $data = array(
    "myaction" => $mcrypt->encrypt($p_how),
    "mymsg" => $mcrypt->encrypt($p_mymsg),
    "iso" => $mcrypt->encrypt($p_iso), //target   
    "phonenumber" => $mcrypt->encrypt($p_phonenumber), //target
    "myiso" => $mcrypt->encrypt($p_myiso), //my   
    "myphonenumber" => $mcrypt->encrypt($p_myphonenumber), //my 
    "mytoken" => $mcrypt->encrypt($myToken), //my 
    "foot" => $mcrypt->encrypt($now)
   );  
 
   $content = json_encode($data);                                  
    
   $post = curl_init();
 
   curl_setopt($post, CURLOPT_REFERER, 'http://' . $myHost .'/');          
   curl_setopt($post, CURLOPT_URL, 'http://apis.airpage.org');
   curl_setopt($post, CURLOPT_POST, true);
   curl_setopt($post, CURLOPT_HTTPHEADER, array("Content-type: application/json"));        
   curl_setopt($post, CURLOPT_POSTFIELDS, $content);       
   curl_setopt($post, CURLOPT_RETURNTRANSFER, true);
 
   $result = curl_exec($post);
   echo $result;
                    
   $json_list= json_decode($result, true);
   curl_close($post);
         
   if(strcmp($json_list['result'],"success") == 0) return 0; //success
 
   return 1; //failed
}   


```

```javascript

$.ajax({
  url : "http://apis.airpage.org/your-access-token/neocancel/friendid",
  dataType : "jsonp",
  type : "GET",
  success : function(r) { console.log(JSON.stringify(r)); },
  error : function(err) { console.log(JSON.stringify(err)); }
});

```

```python

import requests 
URL = 'http://apis.airpage.org/your-access-token/neocancel/your-phone-number/friendid' 
res = requests.get(URL)

if res.status_code is not 200:
  print ("error")
else:
  print ("success")
  print (res.text)

```

> 상기의 명령은 아래와 같이 JSON 구조로 응답합니다:

```json
  {
    "result": "success"
  }
```

친구에게 전화요청을 전송합니다.

### HTTP 요청 

`GET http://apis.airpage.org/[:token]/neocancel/[:friendid]`

### URL 파라메터

파라메터 | 설명
--------- | -----------
token | 부여받은 개발자 토큰값을 입력합니다. 
neocancel | 'neocancel'을 입력합니다. 
friendid | 친구의 아이디를 입력합니다.




# 컴다운 API 사용법 

## 켜져있는 PC목록 요청하기 


```shell

curl "http://apis.airpage.org/your-access-token/comlist"

```

```php

$get = curl_init();
curl_setopt($get, CURLOPT_URL, "http://apis.airpage.org/your-access-token/comlist");
$result = curl_exec($get);
echo $result;

```

```javascript

$.ajax({
  url : "http://apis.airpage.org/your-access-token/comlist",
  dataType : "jsonp",
  type : "GET",
  success : function(r) { console.log(JSON.stringify(r)); },
  error : function(err) { console.log(JSON.stringify(err)); }
});

```

```python

import requests 
URL = 'http://apis.airpage.org/your-access-token/comlist' 
res = requests.get(URL)

if res.status_code is not 200:
  print ("error")
else:
  print ("success")
  print (res.text)

```

> 상기의 명령은 아래와 같이 JSON 구조로 응답합니다:

```json
  { 
		"result":"success","list":

	[
		{"pcname":"AiRPAGE-PC1","localip":"192.168.1.11","time":"2016-04-27 17:00:52"},
		{"pcname":"AiRPAGE-PC2","localip":"192.168.1.12","time":"2016-04-27 19:27:39"}
	]
  }
```

API를 호출하는 호스트의 사설 IP대역에 켜져 있는 PC목록을 요청합니다.

### HTTP 요청 

`GET http://apis.airpage.org/[:token]/comlist`

### URL 파라메터

파라메터 | 설명
--------- | -----------
token | 부여받은 개발자 토큰값을 입력합니다. 
comlist | 'comlist'을 입력합니다. 

<aside class="warning">
GET 형식으로 API가 호출되는 만큼 토큰의 노출에 유의하세요!
</aside>


## 켜져있는 1개 PC정보 요청하기 


```shell

curl "http://apis.airpage.org/your-access-token/comone/192.168.0.8/airpage-pc"

```

```php

$get = curl_init();
curl_setopt($get, CURLOPT_URL, "http://apis.airpage.org/your-access-token/comone/192.168.0.8/airpage-pc");
$result = curl_exec($get);
echo $result;

```

```javascript

$.ajax({
  url : "http://apis.airpage.org/your-access-token/comone/192.168.0.8/airpage-pc",
  dataType : "jsonp",
  type : "GET",
  success : function(r) { console.log(JSON.stringify(r)); },
  error : function(err) { console.log(JSON.stringify(err)); }
});

```

```python

import requests 
URL = 'http://apis.airpage.org/your-access-token/comone/192.168.0.8/airpage-pc' 
res = requests.get(URL)

if res.status_code is not 200:
  print ("error")
else:
  print ("success")
  print (res.text)

```

> 상기의 명령은 아래와 같이 JSON 구조로 응답합니다:

```json
  {	
	"result":"success",	
	"status": "on"
  }
```

API를 호출하는 호스트의 사설 IP대역에 켜져 있는 1개 PC 상태를 요청합니다.

### HTTP 요청 

`GET http://apis.airpage.org/[:token]/comone/[:ip]/[:pcname]`

### URL 파라메터

파라메터 | 설명
--------- | -----------
token | 부여받은 개발자 토큰값을 입력합니다. 
comone | 'comone'을 입력합니다. 
ip | 상태를 알고싶은 PC의 IP주소를 입력합니다. 
pcname | 상태를 알고싶은 PC의 이름을 입력합니다.



## PC 종료 요청하기 


```shell

curl "http://pc-ip-address:pc-port/doaction=PLEASESHUTDOWNNOW&from=API"

```

```php

$get = curl_init();
curl_setopt($get, CURLOPT_URL, "http://pc-ip-address:pc-port/doaction=PLEASESHUTDOWNNOW&from=API");
$result = curl_exec($get);
echo $result;

```

```javascript

$.ajax({
  url : "http://pc-ip-address:pc-port/doaction=PLEASESHUTDOWNNOW&from=API",
  dataType : "jsonp",
  type : "GET",
  success : function(r) { console.log(JSON.stringify(r)); },
  error : function(err) { console.log(JSON.stringify(err)); }
});

```

```python

import requests 
URL = 'http://pc-ip-address:pc-port/doaction=PLEASESHUTDOWNNOW&from=API' 
res = requests.get(URL)

if res.status_code is not 200:
  print ("error")
else:
  print ("success")
  print (res.text)

```

> 상기의 명령은 아래와 같이 JSON 구조로 응답합니다:

```json
  {	
	"result":"success",	
  }
```

API를 호출하는 호스트의 사설 IP대역에 켜져 있는 1개 PC 상태를 요청합니다.

### HTTP 요청 

`GET http://[:ip]/doaction=PLEASESHUTDOWNNOW&from=API`


### URL 파라메터

파라메터 | 설명
--------- | -----------
ip | 종료할 PC의 IP주소를 입력합니다. 
