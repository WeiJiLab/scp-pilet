# scp-pilet
Frontend pilet for Security Check Platform

## Environment Preparing

### Install node and node-sass
```bash
$ brew install node@14 node-sass
```
\* *For now, the node should install version 14 or earlier since the laste sass does not support the version 15 of node.*

### Install Piral CLI
```bash
$ npm i piral-cli -g
```

## Build
### Build Piral Instance
Please build web-shell first since following package in 'package.json' is depend on the output of it.

\* *we will use npm registry to store it to solve this issue*

```json
"devDependencies": {
    ...
    "web-shell": "file:../web-shell/dist/emulator/web-shell-0.0.1.tgz"
}
```

### Build Pilet
```bash
$ npm update --force
$ pilet build
```

## Debug
Pilet project can be debugged without Pilet Instance service, so we need not start the web-shell and sample-pilet-service.

```bash
$ pilet debug
```

## Publish
When the pilet is ready, we need publish it to Pilet Service to make web-shell can use it.

```bash
$ pilet publish --fresh --url <pilet-service-url> --api-key <api-key>
```

\* *for developing at local, we can use 'sample-pilet-service', the \<pilet-service-url\> should be*
```
http://localhost:9000/api/v1/pilet/
```

* *To install 'sample-pilet-service'*
    ```bash
    $ npm install sample-pilet-service -g
    ```

* *Launch 'sample-pilet-service'*
    ```bash
    $ sample-pilet-service
    ```

## Issues
* If you meet following errors, please install or re-install Xcode Command Line Tool
    ```
    npm ERR! No receipt for 'com.apple.pkg.CLTools_Executables' found at '/'.
    npm ERR! 
    npm ERR! No receipt for 'com.apple.pkg.DeveloperToolsCLILeo' found at '/'.
    npm ERR! 
    npm ERR! No receipt for 'com.apple.pkg.DeveloperToolsCLI' found at '/'.
    npm ERR! 
    npm ERR! gyp: No Xcode or CLT version detected!
    ```
    To install Xcode Command Line Tool
    ```bash
    $ xcode-select --install
    ```
    To re-install Xcode Command Line Tool
    ```bash
    $ sudo rm -rf $(xcode-select -print-path)
    $ xcode-select --install
    ```