# Background

1. Use nginx to get access token from cookie. If avaliable, set Authorization: Bearer [access_token]
1. Use ealen/echo-server to simulate the origin API server
1. By convention, the origin API server DNS is origin-[api service]

# Make use of nip as DNS server

1. API service host name: prkwan.[local server ip].nip.io
1. Origin API service host name: origin-prkwan.[local server ip].nip.io

- For example: prkwan.192.168.20.147.nip.io

# How to run

```shell
curl 'http://prkwan.192.168.20.147.nip.io:8888/api/prkwan?verify=cookie' \
-H 'Cookie: access_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOjIsInVzZXJuYW1lIjoibWFyaWEiLCJyb2xlcyI6WyJndWVzdCIsInVzZXIiXSwiaWF0IjoxNjkyMzUxNzU4LCJleHAiOjE2OTIzNTIwNTh9.GOqkLFIqKN2DGXpanBGKfbGfETnbM9ge3-FMltBLyhQ' | jq
```

![sample](sample.png)
