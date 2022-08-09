# Oraclum API Documentation


## /signer
#### Description: ```Get Oraclum Service Signer Address```
#### HTTP Method: ```GET```
#### Example: ```curl -H "Content-Type:application/json"  https://sig.oraclum.io/signer```
#### Response Result:
```json
{
    "signer": "0x00ed0bC0Ea9F54cA00E30B2fA23979De514f7bC9"
}
```
<br/>


## /supported_symbols
#### Description: ```Get Oraclum Service Supported Symbols```
#### HTTP Method: ```GET```
#### Example: ```curl -H "Content-Type:application/json"  https://sig.oraclum.io/supported_symbols```
#### Response Result:
```json
[
    "ALICEUSDT",
    "APEUSDT",
    "AVAXUSDT",
    "AXSUSDT",
    "BABYDOGEUSDT",
    "DOGEUSDT",
    "DOTUSDT",
    "FITFIUSDT",
    "GMTUSDT",
    "SHIBUSDT",
    "SOLUSDT",
    "VOL-BTCUSD",
    "VOL-ETHUSD",
    "VOL-SOLUSD"
]
```
<br/>


## /unsigned
#### Description: ```Get Oraclum Service Symbol Value (without signature)```
#### HTTP Method: ```GET```
#### Example: ```curl -H "Content-Type:application/json"  https://sig.oraclum.io/unsigned?symbols=DOGEUSDT,VOL-BTCUSD```
#### Response Result:
```json
{
    "DOGEUSDT": "0.071111625",
    "VOL-BTCUSD": "0.7502"
}
```
<br/>


## /signed
#### Description: ```Get Oraclum Service Symbol Value (with signature)```
#### HTTP Method: ```GET```
#### Example: ```curl -H "Content-Type:application/json"  https://sig.oraclum.io/signed?symbols=DOGEUSDT,VOL-BTCUSD```
#### Response Result:
```json
[
    {
        "symbol": "DOGEUSDT",
        "symbolId": "0x214dda553a3e2a23944080bfcad3566db70ebe7a599389f0f9cf73f0cf03e933",
        "timestamp": "1660025512",
        "value": "71119249999999992",
        "v": "0x1b",
        "r": "0xe80e64db91ebafd43b6fd10c6c517b0855b8bf73f69ded9b78d7a1a57779f402",
        "s": "0x6c545f1a2dd3ed700d5c1c91ed60a7080eb9a20baefb20b4688d23166fa8fa66"
    },
    {
        "symbol": "VOL-BTCUSD",
        "symbolId": "0x21b5e575db5908f82bf406cb4dd9a5b6c4002f75e43e9a309d52ce4781fd0a4f",
        "timestamp": "1660025512",
        "value": "750100000000000000",
        "v": "0x1b",
        "r": "0x582a29692013b55a906cb9227db3b6955414123b3b9d07b176fd7bd3c84754f3",
        "s": "0x60c604d54eaf1898441073c17ab73160cda2d7754d707c36343cf651ceeb5d60"
    }
]
```
<br/>
