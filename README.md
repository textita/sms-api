
### SMS API 

### Send a sms text message with a http request

### Try out the [SMS API](https://textita.com) for FREE at textita.com




# curl

```
curl -X POST https://textita.com/text \
       --data-urlencode phone='9087938341' \
       --data-urlencode message='Hello world' \
       -d key=textita
```
       
       
# Python

```
 import requests
      requests.post('https://textita.com/text', {
        'phone': '9087938341',
        'message': 'Hello world',
        'key': 'textita',
      })
```      
      
      
# Ruby

```
require 'net/http'
      require 'uri'

      uri = URI.parse("https://textita.com/text")
      Net::HTTP.post_form(uri, {
        :phone => '9087938341',
        :message => 'Hello world',
        :key => 'textita',
      })
```

# Node.js

```
var request = require('request');

request.post('https://textita.com/text', {
  form: {
    phone: '9087938341',
    message: 'Hello world',
    key: 'textita',
  },
}, function(err, httpResponse, body) {
  if (err) {
    console.error('Error:', err);
    return;
  }
  console.log(JSON.parse(body));
})
```       
       
 # PHP
 
``` 
 $ch = curl_init('https://textita.com/text');
$data = array(
  'phone' => '9087938341',
  'message' => 'Hello world',
  'key' => 'textita',
);

curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS, http_build_query($data));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

$response = curl_exec($ch);
curl_close($ch);

```

# C#

```

using System;
using System.Collections.Specialized;
using System.Net;

using (WebClient client = new WebClient())
{
  byte[] response = client.UploadValues("https://textita.com/text", new NameValueCollection() {
    { "phone", "9087938341" },
    { "message", "Hello world" },
    { "key", "textita" },
  });

  string result = System.Text.Encoding.UTF8.GetString(response);
}

```

# Java

```

final NameValuePair[] data = {
    new BasicNameValuePair("phone", "9087938341"),
    new BasicNameValuePair("message", "Hello world"),
    new BasicNameValuePair("key", "textita")
};
HttpClient httpClient = HttpClients.createMinimal();
HttpPost httpPost = new HttpPost("https://textita.com/text");
httpPost.setEntity(new UrlEncodedFormEntity(Arrays.asList(data)));
HttpResponse httpResponse = httpClient.execute(httpPost);

String responseString = EntityUtils.toString(httpResponse.getEntity());
JSONObject response = new JSONObject(responseString);

```

# Powershell

```

$body = @{
  "phone"="9087938341"
  "message"="Hello World"
  "key"="textita"
}
$submit = Invoke-WebRequest -Uri https://textita.com/text -Body $body -Method Post

```

# Golang

```
import (
  "net/http"
  "net/url"
)

func main() {
  values := url.Values{
    "phone": {"9087938341"},
    "message": {"Hello world"},
    "key": {"textita"},
  }

  http.PostForm("https://textita.com/text", values)
}
```
