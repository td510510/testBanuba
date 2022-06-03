# Banuba SDK Web AR demo app  
  
**Important**  
Please use [v0.x](../../tree/v0.x) branch for SDK version 0.x (e.g. v0.38).  
    
## Requirements

- The [latest](#obtaining-banuba-sdk-web-ar) Banuba SDK Web AR release
- Banuba [client token](#obtaining-banuba-client-token)
- [Nodejs](https://nodejs.org/en/) installed
- Browser with support of [WebGL 2.0](https://caniuse.com/#feat=webgl2)

### Obtaining Banuba SDK Web AR

To get the latest Banuba SDK Web AR release please fill in the [form on banuba.com](https://www.banuba.com/face-filters-sdk) website, or contact us via [info@banuba.com](mailto:info@banuba.com).

### Obtaining Banuba Client token

Banuba Client token is required to get Banuba SDK Web AR working.

Generally it's delivered with Banuba SDK Web AR archive.

To receive a new **trial** client token please fill in the [form on banuba.com](https://www.banuba.com/face-filters-sdk) website, or contact us via [info@banuba.com](mailto:info@banuba.com).

## Environment setup and local run

Clone the repository

```sh
git clone git@github.com:Banuba/quickstart-web.git
```

Put Banuba SDK Web AR [files](#obtaining-banuba-sdk-web-ar) into the cloned folder

```diff
quickstart-web/
   effects/
   BanubaClientToken.js
+  BanubaSDK.data
+  BanubaSDK.js
+  BanubaSDK.wasm
+  BanubaSDK.simd.wasm
   index.html
   README.md
   styles.css
```

Insert Banuba [client token](#obtaining-banuba-client-token) into `BanubaClientToken.js`

```js
window.BANUBA_CLIENT_TOKEN = "PUT YOUR CLIENT TOKEN HERE"
```

Run the live server in the cloned folder
```sh
npx live-server
```

Open [localhost:8080](http://localhost:8080)

## Adding a new effect

Zip the effect folder and put it under the `effects/` subfolder
```diff
quickstart-web/
   effects/
     BackgroundPicture.zip
     BackgroundBeauty.zip
     BigPinkGlasses.zip
     glasses_Banuba.zip
     Hipster3.zip
+    NewEffect.zip
     Hair_recoloring.zip
   BanubaClientToken.js
   BanubaSDK.data
   BanubaSDK.js
   BanubaSDK.wasm
   BanubaSDK.simd.wasm
   index.html
   README.md
   styles.css
```

Add the effect name into `effects` array at [index.html, line 65](/index.html#L65)

```diff
<script type="module">
  import { Effect, Webcam, Player, VideoRecorder, ImageCapture, Dom } from "./BanubaSDK.js"

  const effects = [
+   "NewEffect",
    "BackgroundPicture",
    "BackgroundBeauty",
    "BigPinkGlasses",
    "glasses_Banuba",
    "Hipster3",
    "Hair_recoloring"
  ]
```