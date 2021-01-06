# scp-pilet
Frontend pilet for Security Check Platform

## Build
```bash
$ npm update --force
$ pilet build
```

## Debug
```bash
$ pilet debug
```

## Publish
```bash
$ pilet publish --fresh --url <pilet-service-url> --api-key <api-key>
```


for developing at local, we can use 'sample-pilet-service', the URL will be
```
http://localhost:9000/api/v1/pilet/
```

**To install 'sample-pilet-service'**
```bash
$ npm install sample-pilet-service -g
```

**Launch 'sample-pilet-service'**
```bash
$ sample-pilet-service
```