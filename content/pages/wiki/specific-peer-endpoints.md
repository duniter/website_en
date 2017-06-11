Title: Specific peer endpoints
Order: 9
Date: 2017-03-31
Slug: specific-peer-endpoints
Authors: cgeek

> Quoted from [commentaire sur le ticket GitHub #337](https://github.com/duniter/duniter/issues/337#issuecomment-251380492).

### Add an endpoint

```
duniter config --addep "SUPER_ENDPOINT_ELASTIC_SEARCH cgeek.fr blablabla 21020"
```

Ce qui produit :

```json
{
  "version": 2,
  "currency": "test_net",
  "endpoints": [
    "BASIC_MERKLED_API cgeek.fr 88.174.120.187 2a01:e35:8ae7:8bb0:b468:a0c:a607:379f 9330",
    "BASIC_MERKLED_API 88.174.120.187 9333",
    "SUPER_ENDPOINT_ELASTIC_SEARCH cgeek.fr blablabla 21020"
  ],
  "block": "44041-0000297B14119AC6710D493D773821B11E016DBE317E778FF8B0B5BC347B8039",
  "signature": "tgNB44JiHBuP3G1DsQthkTFBrghNX7me1R5XACx15SQ1RC39yuqhaHWhy94rYttJRgsWNPOQPRmfuEDs6bM7BQ==",
  "pubkey": "HnFcSms8jzwngtVomTTnzudZx7SHUQY8sVE1y8yBmULk"
}
```

### Remove an endpoint

```
duniter config --remep "SUPER_ENDPOINT_ELASTIC_SEARCH cgeek.fr blablabla 21020"
```

Results in : 

```json
{
  "version": 2,
  "currency": "test_net",
  "endpoints": [
    "BASIC_MERKLED_API cgeek.fr 88.174.120.187 2a01:e35:8ae7:8bb0:b468:a0c:a607:379f 9330",
    "BASIC_MERKLED_API 88.174.120.187 9333"
  ],
  "block": "44041-0000297B14119AC6710D493D773821B11E016DBE317E778FF8B0B5BC347B8039",
  "signature": "tgNB44JiHBuP3G1DsQthkTFBrghNX7me1R5XACx15SQ1RC39yuqhaHWhy94rYttJRgsWNPOQPRmfuEDs6bM7BQ==",
  "pubkey": "HnFcSms8jzwngtVomTTnzudZx7SHUQY8sVE1y8yBmULk"
}
```

### Cautious

A good practice is to realize these operations **exclusively on only one node**, which will take care to handle specific endpoints. Because if you have : 

* a node which add the endpoint `EP1`
* *another* node which adds the endpoint `EP1`

Then you will fall in a never ending [ping-pong loop](/cles-partagees#le-stock-de-blockstamp), which will consume all your available stock of timestamps to issue new peer documents. Thus, you won't be able to update your peer document before another block gets computed.
