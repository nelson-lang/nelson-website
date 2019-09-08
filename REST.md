## RESTfull web service


Convert Data/download from Web Service

Examples:

```
// read an distant audio file
options = weboptions();
options.ContentType = 'audio';
[y, fs] = webread('https://ccrma.stanford.edu/~jos/wav/Latin.wav', options);
playerObj = audioplayer(y, fs);
play(playerObj)
playerObj
```

```
// read data from National Agricultural Statistics Service
url = 'https://quickstats.nass.usda.gov/api/api_GET/?key=1C757E50-5169-30CC-BEFD-40A5C3E2A43D&format=JSON&or_desc=CROPS&domain_desc=TOTAL&agg_level_desc=COUNTY&state_name=ALABAMA&county_name=AUTAUGA&year=2012';
options = weboptions('UserAgent', 'http://www.whoishostingthis.com/tools/user-agent/'); 
s = webread(url, options);
s.data
```

![Get data from Netatmo weather station](https://github.com/Nelson-numerical-software/nelson-website/raw/master/images/netatmo.png "Netatmo")

![Send a message to Slack](https://github.com/Nelson-numerical-software/nelson-website/raw/master/images/slack.png "Slack")


[Previous page](FEATURES.md)