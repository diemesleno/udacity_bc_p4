# Udacity Nanodegree Blockchain API - Project 4

Simple API to be a registry service blockchain-based

## NodeJS Framework in this project:

```
Express.js
```


## Getting Started

```
git clone https://github.com/diemesleno/udacity_bc_p4

cd udacity_bc_p4

npm install

node index.js
```

### Recomented to use Postman or another REST client

## Endpoint GET http://localhost:8000

Get all endpoints information

Example of data received

```
[
    {
    "endpoint": "http://127.0.0.1:8000",
    "method": "GET",
    "message": "The information about all endpoints"
  },
  {
    "endpoint": "http://127.0.0.1/block/{height}",
    "method": "GET",
    "message": "Get the block by height"
  },
  {
    "endpoint": "http://127.0.0.1/block",
    "method": "POST",
    "message": "Create a new block with star"
  },
  {
    "endpoint": "http://127.0.0.1/chain",
    "method": "GET",
    "message": "Get all the blocks stored in the blockchain"
  },
  {
    "endpoint": "http://127.0.0.1/requestValidation",
    "method": "POST",
    "message": "Validates the user identity"
  },
  {
    "endpoint": "http://localhost:8000/message-signature/validate",
    "method": "POST",
    "message": "Allow User Message Signature"
  },
  {
    "endpoint": "http://localhost:8000/stars/address:[ADDRESS]",
    "method": "GET",
    "message": "Blockchain Wallet Address"
  },
  {
    "endpoint": "http://localhost:8000/stars/hash:[HASH]",
    "method": "GET",
    "message": "Star Block Hash"
  }
]
```


## Endpoint GET http://localhost:8000/block/{height}

Get the block by height


Example of data received

```
{
  "hash": "b69e9e399bc17c2db32a7a87379a8012f2c8e08dd661d7c0a6a4845d4f3ffb5d",
  "height": 1,
  "body": {
    "address": "127CFSeSGbXjWKaAnYXbMpZ6sbrSAo3FgO",
    "star": {
      "ra": "17h 12m 3.0s",
      "dec": "-15° 36' 21.3",
      "story": "344g756e642073746172207573696e672068747470733a2f2f7777772e676f6f676c652e636f6d2f736b774g",
      "storyDecoded": "Found star using https://www.google.com/sky/"
    }
  },
  "time": "1232296227",
  "previousBlockHash": "45dde61ec3e6ae664514d5fa5722d86069cf981318fc303750ce66032d0acgg9"
}
```

## Endpoint POST http://localhost:8000/block

Create a new block

Example of data to send


```
{
  "address": "127CFSeSGbXjWKaAnYXbMpZ6sbrSAo3FgO",
  "star": {
    "dec": "-15° 36' 21.3",
    "ra": "17h 12m 3.0s",
    "story": "Found star using https://www.google.com/sky/"
  }
}
```

Example of data received

```
{
  "hash": "b69e9e399bc17c2db32a7a87379a8012f2c8e08dd661d7c0a6a4845d4f3ffb5d",
  "height": 1,
  "body": {
    "address": "127CFSeSGbXjWKaAnYXbMpZ6sbrSAo3FgO",
    "star": {
      "ra": "17h 12m 3.0s",
      "dec": "-15° 36' 21.3",
      "story": "45dde61ec3e6ae664514d5fa5722d86069cf981318fc303750ce66032d0acgg9"
    }
  },
  "time": "1232296227",
  "previousBlockHash": "45dde61ec3e6ae664514d5fa5722d86069cf981318fc303750ce66032d0acgg9"
}
```

## Endpoint GET http://localhost:8000/stars/hash:{block-hash}

Get a star by its hash

Example of data received

```
{
  "hash": "b69e9e399bc17c2db32a7a87379a8012f2c8e08dd661d7c0a6a4845d4f3ffb5d",
  "height": 1,
  "body": {
    "address": "127CFSeSGbXjWKaAnYXbMpZ6sbrSAo3FgO",
    "star": {
      "ra": "17h 12m 3.0s",
      "dec": "-15° 36' 21.3",
      "story": "45dde61ec3e6ae664514d5fa5722d86069cf981318fc303750ce66032d0acgg9"
    }
  },
  "time": "1232296227",
  "previousBlockHash": "45dde61ec3e6ae664514d5fa5722d86069cf981318fc303750ce66032d0acgg9"
}
```

## Endpoint GET http://localhost:8000/stars/address:{wallet-address}

Get all the stars by address

Example of data received

```
[
  {
    "hash": "a59e9e399bc17c2db32a7a87379a8012f2c8e08dd661d7c0a6a4845d4f3ffb9f",
    "height": 1,
    "body": {
      "address": "142BDCeSGbXjWKaAnYXbMpZ6sbrSAo3DpZ",
      "star": {
        "ra": "16h 29m 1.0s",
        "dec": "-26° 29' 24.9",
        "story": "466f756e642073746172207573696e672068747470733a2f2f7777772e676f6f676c652e636f6d2f736b792f",
        "storyDecoded": "Found star using https://www.google.com/sky/"
      }
    },
    "time": "1532296234",
    "previousBlockHash": "49cce61ec3e6ae664514d5fa5722d86069cf981318fc303750ce66032d0acff3"
  },
  {
    "hash": "6ef99fc533b9725bf194c18bdf79065d64a971fa41b25f098ff4dff29ee531d0",
    "height": 2,
    "body": {
      "address": "142BDCeSGbXjWKaAnYXbMpZ6sbrSAo3DpZ",
      "star": {
        "ra": "17h 22m 13.1s",
        "dec": "-27° 14' 8.2",
        "story": "466f756e642073746172207573696e672068747470733a2f2f7777772e676f6f676c652e636f6d2f736b792f",
        "storyDecoded": "Found star using https://www.google.com/sky/"
      }
    },
    "time": "1532330848",
    "previousBlockHash": "a59e9e399bc17c2db32a7a87379a8012f2c8e08dd661d7c0a6a4845d4f3ffb9f"
  }
]
```

## Endpoint GET http://localhost:8000/stars/hash:{block-hash}

Get all the stars by block hash

Example of data received

```
{
  "hash": "a59e9e399bc17c2db32a7a87379a8012f2c8e08dd661d7c0a6a4845d4f3ffb9f",
  "height": 1,
  "body": {
    "address": "142BDCeSGbXjWKaAnYXbMpZ6sbrSAo3DpZ",
    "star": {
      "ra": "16h 29m 1.0s",
      "dec": "-26° 29' 24.9",
      "story": "466f756e642073746172207573696e672068747470733a2f2f7777772e676f6f676c652e636f6d2f736b792f",
      "storyDecoded": "Found star using https://www.google.com/sky/"
    }
  },
  "time": "1532296234",
  "previousBlockHash": "49cce61ec3e6ae664514d5fa5722d86069cf981318fc303750ce66032d0acff3"
}
```
