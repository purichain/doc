# PURICHAIN API DOCS

## 1. Trade
### 1.1 Market Supply
> {api_url}/account/marketsupply?tAccountAction=0
```javascript
{
    "errorCode": 0,
    "contents": {
        "timestamp": 1665636696658,
        "action": 0,
        "name": "PURI",
        "symbol": "pure",
        "totalSupply": "100000000000.000000000",
        "marketSupply": "2400000000.000000000"
    }
}
```
   
   
### 1.2 Trade Volume Per Day
> {api_url}/account/trade/day?tAccountAction=0
```javascript
{
    "errorCode": 0,
    "contents": {
        "timestamp": 1665637788186,
        "action": 0,
        "name": "PURI",
        "symbol": "pure",
        "tradePerDay": "102.000000000"
    }
}
```
   
   
### 1.3 Transactions Per Day
> {api_url}/sc/txs/day?tAccountAction=0
```javascript
{
    "errorCode": 0,
    "contents": {
        "timestamp": 1665637811146,
        "txsCnt": "7"
    }
}
```
   
   
### 1.4 Transaction History
> {api_url}/sc/txs/history?tAccountAction=0&interval=DAY&period=2
```javascript
{
    "errorCode": 0,
    "contents": {
        "timestamp": 1665637902318,
        "historyList": [
            {
                "index": 0,
                "txsCnt": "7",
                "sttMs": 1665551502316,
                "endMs": 1665637902316
            },
            {
                "index": 1,
                "txsCnt": "0",
                "sttMs": 1665465102316,
                "endMs": 1665551502316
            }
        ]
    }
}
```
   
   * * *
   
## 2. Blocks
### 2.1 The Latest Blocks
> {api_url}/block/latest?cnt=1
```javascript
{
    "errorCode": 0,
    "contents": {
        "res": true,
        "totalBlkCnt": "7271038",
        "latestBlks": [
            {
                "subnet_id": 24588,
                "blk_num": "7271038",
                "p2p_addr": "2677811144576204800",
                "bgt": "1665637675612",
                "pbh": "FD7E789F779CEDC3ECB121F10F13AAAA354C33B81DD09BBE14CBDC17943FB652",
                "tx_cnt": 0,
                "blk_hash": "B636E842D8D297DB222B3C877F600AF5AF07BF86A5BDF66F6BF43F26D583B331",
                "sig": "FCF373AF5C698B66824E23B7DB2C2A5683CF5C4BE998F00429998BFD041C152F7C410AB6B22C3B24155E6D0D425DCD2D40706B729421C2A3BA53AD1C8B8B3D05",
                "pubkey": "05727B2499DC58E67947DAFF2F13FEC9E320894514BCEF4F392A1E2FBC20D3CD18",
                "bct": "0"
            }
        ]
    }
}
```
   
   
### 2.2 The Block Information
check the information with a *block number* or a *block hash*
> {api_url}/block/blkinfo?blkNum=1
> {api_url}/block/blkinfo?blkHash=035BF05F8999C775D712784CC5BB4475F70A466A798CA76F61994700F9E8A9D3
```javascript
{
    "errorCode": 0,
    "contents": {
        "res": true,
        "blkInfo": {
            "subnet_id": 24580,
            "blk_num": "1",
            "p2p_addr": "2684003555408609280",
            "bgt": "1655952525793",
            "pbh": "0000000000000000000000000000000000000000000000000000000000000000",
            "tx_cnt": 1,
            "blk_hash": "035BF05F8999C775D712784CC5BB4475F70A466A798CA76F61994700F9E8A9D3",
            "sig": "D321279E7A25FA695BD2A477506C6BBFBD80087A6ADD6478F4038FAF5A8F5BE140B895DDD713C0DCE123C4F1821742813F8F455B4139CAB1DD714A9FB7E76909",
            "pubkey": "05382160319F6ADB4C514BC2C579528932A60F954445720BECA4A5C82A7A5F54E4",
            "bct": "0"
        }
    }
}
```
   
   
### 2.3 The Count of Blocks
> {api_url}/block/blkcnt
```javascript
{
    "errorCode": 0,
    "contents": {
        "res": true,
        "totalBlkCnt": "7270924",
        "lastBN": "7270924",
        "totalBlk24hCnt": 64893
    }
}
```
   
   * * *
   
## 3. Smart Contracts - Transactions
### 3.1 The Smart Contract Information
check smart contract with a *block number*
> {api_url}/sc/txs/info?blkNum=1&cnt=10
```javascript
{
    "errorCode": 0,
    "contents": {
        "res": true,
        "blkNum": "1",
        "dbKeyInfo": {
            "min_db_key": "6918654927547924480",
            "max_db_key": "6918654927547924480"
        },
        "totalTxsCnt": "1",
        "scTxsInfo": [
            {
                "db_key": "6918654927547924480",
                "from_account": "0",
                "to_account": "0",
                "action": 2147483648,
                "c_action": 4294967295,
                "amount": "0",
                "sc_hash": "5d3691aed3b1495cc6c086a907c5875172fcef045731887c7a42b0b2332765ae",
                "blk_num": "1",
                "subnet_id": 24580,
                "contract": "{\"create_tm\":\"1655952484067\",\"fintech\":\"0\",\"privacy\":\"0\",\"fee\":\"0\",\"from_account\":\"0000000000000000\",\"to_account\":\"0000000000000000\",\"action\":2147483648,\"contents\":{\"owner_pk\":\"056cab6d5cf7b133b252034bb622f21fa5ce86afd77811fa8ec84ae03ef7a354ac\",\"super_pk\":\"056cab6d5cf7b133b252034bb622f21fa5ce86afd77811fa8ec84ae03ef7a354ac\",\"action\":0,\"name\":\"PURI\",\"symbol\":\"pure\",\"total_supply\":\"100000000000.000000000\",\"decimal_point\":9,\"lock_time_from\":\"0\",\"lock_time_to\":\"0\",\"lock_transfer\":0,\"black_list\":\"\",\"functions\":\"\"},\"memo\":\"\",\"sig\":\"374A205D077C702DE79E67DCE510F58CC8BAF228BAADCDC094A880766F709FC849581D468314604A6A0A6929EEBE50CF8E9B341263A004FF8ED2F95ACAE7140A\",\"signed_pubkey\":\"056cab6d5cf7b133b252034bb622f21fa5ce86afd77811fa8ec84ae03ef7a354ac\"}"
            }
        ]
    }
}
```
   
   
check smart contract with a *transaction hash*
> {api_url}/sc/txs/info?scHash=5d3691aed3b1495cc6c086a907c5875172fcef045731887c7a42b0b2332765ae
```javascript
{
    "errorCode": 0,
    "contents": {
        "res": true,
        "scHash": "5d3691aed3b1495cc6c086a907c5875172fcef045731887c7a42b0b2332765ae",
        "scTxsInfo": {
            "subnet_id": 24580,
            "create_tm": "1655952484067",
            "db_key": "6918654927547924480",
            "confirmed": 1,
            "from_account": "0",
            "to_account": "0",
            "action": 2147483648,
            "c_action": 4294967295,
            "dst_account": "0",
            "amount": "0",
            "signed_pubkey": "056cab6d5cf7b133b252034bb622f21fa5ce86afd77811fa8ec84ae03ef7a354ac",
            "err_code": 0,
            "contract": "{\"create_tm\":\"1655952484067\",\"fintech\":\"0\",\"privacy\":\"0\",\"fee\":\"0\",\"from_account\":\"0000000000000000\",\"to_account\":\"0000000000000000\",\"action\":2147483648,\"contents\":{\"owner_pk\":\"056cab6d5cf7b133b252034bb622f21fa5ce86afd77811fa8ec84ae03ef7a354ac\",\"super_pk\":\"056cab6d5cf7b133b252034bb622f21fa5ce86afd77811fa8ec84ae03ef7a354ac\",\"action\":0,\"name\":\"PURI\",\"symbol\":\"pure\",\"total_supply\":\"100000000000.000000000\",\"decimal_point\":9,\"lock_time_from\":\"0\",\"lock_time_to\":\"0\",\"lock_transfer\":0,\"black_list\":\"\",\"functions\":\"\"},\"memo\":\"\",\"sig\":\"374A205D077C702DE79E67DCE510F58CC8BAF228BAADCDC094A880766F709FC849581D468314604A6A0A6929EEBE50CF8E9B341263A004FF8ED2F95ACAE7140A\",\"signed_pubkey\":\"056cab6d5cf7b133b252034bb622f21fa5ce86afd77811fa8ec84ae03ef7a354ac\"}"
        }
    }
}
```
   
   
### 3.2 The Latest Transactions
> {api_url}/sc/latest?cnt=1
```javascript
{
    "errorCode": 0,
    "contents": {
        "res": true,
        "totalTxsCnt": "87",
        "latestScTxs": [
            {
                "create_tm": "1665636381792",
                "db_key": "6918654927547924566",
                "confirmed": 1,
                "from_account": "5879462354708954388",
                "to_account": "8185305063275948285",
                "dst_account": "8185305063275948285",
                "action": 2147483651,
                "c_action": 0,
                "amount": "12.000000000",
                "sc_hash": "0a3fbf9f48263124d635bfbf50b5942d8ff772a1ea30c24c3a80a179f162bdff",
                "blk_num": "7270067",
                "subnet_id": 24580,
                "contract": "{\"create_tm\":\"1665636381792\",\"fintech\":\"1\",\"privacy\":\"0\",\"fee\":\"0\",\"from_account\":\"51980bdc62b57d14\",\"to_account\":\"71980b9662c4e8fd\",\"action\":2147483651,\"contents\":{\"action\":0,\"amount\":\"12.000000000\"},\"memo\":\"\",\"sig\":\"E5A5C0ED4CBA791FCF94BEFC05A8CF81531AF327D67D7BB90D0CD4FBD12FBEDDACC337EBED2933752C998E5C21D58D4531261D42E0EF4F33D9166CDD99820F0F\",\"signed_pubkey\":\"058e7a4898d04169f570d0caa8cab0330dce12a45cb36aec6ef4fb23917dcc142c\"}"
            }
        ]
    }
}
```
   
   
### 3.3 Total Counts of Transactions
> {api_url}/sc/txs/all?tAccountAction=0
```javascript
{
    "errorCode": 0,
    "contents": {
        "timestamp": 1665637824010,
        "txsCnt": "72",
        "txs24hCnt": "7"
    }
}
```
   
   * * *
   
## 4. Accounts
### 4.1 Detail of the Account
**Token Account**   
   
check details with an *account number*
> {api_url}/account/chk/info?accountNum=1152921504606846976

check details with the *name* or the *symbol* of Token
> {api_url}/account/chk/info?tokenName=PURI&tokenSymbol=PURE
```javascript
{
    "errorCode": 0,
    "contents": {
        "timestamp": 1665637150855,
        "tAccountTxsCnt": "1",
        "tAccountInfo": {
            "subnet_id": 24580,
            "idx": "1",
            "create_tm": "1655952484067",
            "blk_num": "1",
            "db_key": "6918654927547924480",
            "owner_pk": "056cab6d5cf7b133b252034bb622f21fa5ce86afd77811fa8ec84ae03ef7a354ac",
            "super_pk": "056cab6d5cf7b133b252034bb622f21fa5ce86afd77811fa8ec84ae03ef7a354ac",
            "account_num": "1152921504606846976",
            "action": 0,
            "name": "PURI",
            "symbol": "pure",
            "total_supply": "100000000000.000000000",
            "market_supply": "2400000000.000000000",
            "decimal_point": 9,
            "lock_time_from": "0",
            "lock_time_to": "0",
            "lock_transfer": 0,
            "black_list": "",
            "functions": ""
        }
    }
}
```
   
   
**User Account**
> {api_url}/account/chk/info?accountNum=2420697626140044552
```javascript
{
    "errorCode": 0,
    "contents": {
        "timestamp": 1665637228527,
        "uAccountTxsCnt": "57",
        "uAccountInfo": {
            "subnet_id": 24580,
            "idx": "1",
            "create_tm": "1656057095389",
            "blk_num": "78568",
            "db_key": "6918654927547924481",
            "owner_pk": "052654b5b2690405d2c1ac524522f79e1d4592f15d71beaa9f53c2f7a48ea00993",
            "super_pk": "052654b5b2690405d2c1ac524522f79e1d4592f15d71beaa9f53c2f7a48ea00993",
            "account_num": "2420697626140044552",
            "account_id": "USER_01"
        },
        "numOfTokens": 1,
        "uAccountBalance": [
            {
                "subnet_id": 24580,
                "idx": "140",
                "create_tm": "1665636366871",
                "blk_num": "7270055",
                "db_key": "6918654927547924565",
                "my_account_num": "2420697626140044552",
                "account_num": "5879462354708954388",
                "action": 0,
                "name": "PURI",
                "symbol": "pure",
                "amount": "-15.000000000",
                "balance": "2399999175.000000000"
            }
        ],
        "uAccountBalancePrv24h": [
            {
                "subnet_id": 24580,
                "idx": "128",
                "create_tm": "1664329530162",
                "blk_num": "6288548",
                "db_key": "6918654927547924559",
                "my_account_num": "2420697626140044552",
                "account_num": "4726540609591448078",
                "action": 0,
                "name": "PURI",
                "symbol": "pure",
                "amount": "-15.000000000",
                "balance": "2399999265.000000000"
            }
        ],
        "uAccountBalancePrv30d": [
            {
                "subnet_id": 24580,
                "idx": "114",
                "create_tm": "1660197531933",
                "blk_num": "3186279",
                "db_key": "6918654927547924551",
                "my_account_num": "2420697626140044552",
                "account_num": "5879462354708954388",
                "action": 0,
                "name": "PURI",
                "symbol": "pure",
                "amount": "-15.000000000",
                "balance": "2399999340.000000000"
            }
        ]
    }
}
```
   
   
### 4.2 Holders of the Token
> {api_url}/account/richlist?tAccountAction=0&cnt=1
```javascript
{
    "errorCode": 0,
    "contents": {
        "res": true,
        "action": 0,
        "name": "PURI",
        "symbol": "pure",
        "market_supply": "2400000000.000000000",
        "totalAccountNum": "14",
        "richList": [
            {
                "subnet_id": 24580,
                "idx": "140",
                "create_tm": "1665636366871",
                "blk_num": "7270055",
                "db_key": "6918654927547924565",
                "my_account_num": "2420697626140044552",
                "account_num": "5879462354708954388",
                "action": 0,
                "name": "PURI",
                "symbol": "pure",
                "amount": "-15.000000000",
                "balance": "2399999175.000000000"
            }
        ]
    }
}
```
   
   
### 4.3 Total Counts of Accounts
> {api_url}/account/list?total
```javascript
{
    "errorCode": 0,
    "contents": {
        "timestamp": 1665637863340,
        "tAccountTotalCnt": "1",
        "uAccountTotalCnt": "14",
        "tAccount24hCnt": "0",
        "uAccount24hCnt": 0
    }
}
```
