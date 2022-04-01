# Oraclum API Documentation


## /get_version
#### Description: ```Get Oraclum Service Version```
#### HTTP Method: ```GET```
#### Example: ```curl -H "Content-Type:application/json"  https://api.oraclum.io/get_version```
#### Response Result:
```json
{
    "data": {
        "version": 1.0
    },
    "status": 200
}
or
{
    "data": {},
    "message":"$errormessage",
    "status": "$errorcode"
}
```
<br/>


## /get_basic_info
#### Description: ```Get Oraclum Service Basic Info ```
#### HTTP Method: ```GET ```
#### Example: ```curl -H "Content-Type:application/json"  https://api.oraclum.io/get_basic_info```
#### Response Result:
```json
{
    "data": {
        "signer_address": "0xBfF0Bab15d23651e058f3a5441c9060AF4eB6E7A"
    },
    "status": 200
}
or
{
    "data": {},
    "message":"$errormessage",
    "status": "$errorcode"
}
```
<br/>


## /get_supported_symbols
#### Description: ```Get Oraclum Service Supported Symbols```
#### HTTP Method: ```GET```
#### Example: ```curl -H "Content-Type:application/json"  https://api.oraclum.io/get_supported_symbols```
#### Response Result:
```json
{
    "data": [
        "BTCUSD",
        "ETHUSD",
        "GHSTUSDT",
        ...
        ...
        "APEUSDT",
        "GMTUSDT",
        "VOL-BTCUSD",
        "VOL-ETHUSD"
    ],
    "status": 200
}
or
{
    "data": {},
    "message":"$errormessage",
    "status": "$errorcode"
}
```
<br/>


## /get_symbol_data
#### Description: ```Get Oraclum Service Symbol Data```
#### HTTP Method: ```GET, POST```
#### Example(GET): ```curl -H "Content-Type:application/json"  https://api.oraclum.io/get_symbol_data?symbol=VOL-BTCUSD```
#### Example(POST): ```curl -H "Content-Type:application/json"  https://api.oraclum.io/get_symbol_data  -X POST -d "[\"GMTUSDT\",\"VOL-BTCUSD\"]"```
#### Response Result:
```json
{
    "data": {
        "GMTUSDT": {
            "messageHash": "0x1e0007c6c461e65bbef17ec31d93ee5dfb23a11b94b00d2e7aedef6121e6ebe6",
            "r": "0x8daac62e132807d22d56fbaefb53df4e0d25e35fce2237bc3cfe9faadb0b2b00",
            "s": "0x1f45b1c59e62368eee52e7206f3c6d6a2c73e25a2f2188209c140010febe9105",
            "signature": "0x8daac62e132807d22d56fbaefb53df4e0d25e35fce2237bc3cfe9faadb0b2b001f45b1c59e62368eee52e7206f3c6d6a2c73e25a2f2188209c140010febe91051c",
            "symbolId": "0xc199c9161c951cb238f18c0165a14c039761d4aa6981272c853cb49970610816",
            "symbolName": "GMTUSDT",
            "timestamp": "1648537440",
            "v": "0x1c",
            "value": "1037110000000000000"
        },
        "VOL-BTCUSD": {
            "messageHash": "0x54c7cbfd752624b3b2a2151c99330c28a53ab2d0d0c1b4e9488d767de2414638",
            "r": "0x1f233b0b91c30d20a696f624ea2f2ebe96fb3cfef2245b4339345ae3b11e9bcb",
            "s": "0x7669e7cae6756131bd69a00e667942d016e3ea657abb9c2eb730fea6443ea509",
            "signature": "0x1f233b0b91c30d20a696f624ea2f2ebe96fb3cfef2245b4339345ae3b11e9bcb7669e7cae6756131bd69a00e667942d016e3ea657abb9c2eb730fea6443ea5091b",
            "symbolId": "0x21b5e575db5908f82bf406cb4dd9a5b6c4002f75e43e9a309d52ce4781fd0a4f",
            "symbolName": "VOL-BTCUSD",
            "timestamp": "1648537140",
            "v": "0x1b",
            "value": "621700000000000000"
        }
    },
    "status": 200
}
or
{
    "data": {},
    "message":"$errormessage",
    "status": "$errorcode"
}
```
<br/>
