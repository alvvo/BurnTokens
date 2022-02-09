### Поиск код-хэша индексов
```
tonos-cli --url <сеть> run <адрес_коллекции> resolveCodeHashIndex '{"addrRoot": "<адрес_коллекции>", "addrOwner": "<адрес_владельца>"}' --abi <abi_коллекции>
```
* Подставим значения:
    * __сеть__: https://main.ton.dev
    * __адрес_коллекции__: 0:f863e345c0c0a078a9a3bbe58bc93ca9a09898a228fb1e8315d2a51970670446
    * __адрес_владельца__: -1:efd5a14409a8a129686114fc092525fddd508f1ea56d1b649a3a695d3a5b188c
    * __abi_коллекции__:
    ```
    // функция из abi

    {
		"name": "resolveCodeHashIndex",
		"inputs": [
			{"name":"addrRoot","type":"address"},
			{"name":"addrOwner","type":"address"}
			],
		"outputs": [
			{"name":"codeHashIndex","type":"uint256"}
		]
	},
    ```
* Полученный код-хэш:   
    ```
    0x8d639f95cc20f9863f1b08e893c786f0c55c2c0bd0d659aef4a3a4929c0599ba
    ```
### Сколько токенов было сожжено
* В ссылку вставляем наш код-хэш без `0x`:
```
https://ever.live/contracts/contractDetails?codeHash=<code_hash>
```
* Получаем:
https://ever.live/contracts/contractDetails?codeHash=8d639f95cc20f9863f1b08e893c786f0c55c2c0bd0d659aef4a3a4929c0599ba
* Параметр __Развернутые контракты__ и является количеством токенов который были сожжены.