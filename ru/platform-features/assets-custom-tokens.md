# Ассеты

Ассеты - это своего рода цифровой актив, который имеет определенное консенсусное значение. Платформа Waves позволяет пользователям 
создавать свои собственные токены для удовлетворения их конкретных потребностей.

# 1. Выпуск своего токена {#Assets(customtokens)-IssuingyourownToken}

Платформа Waves позволяет бизнесу выпускать свои токены для любых имеющихся потребностей. Выпуская токены, бизнес может 
создать внутреннюю цифровую валюту через блокчейн. Таким образом, он может использовать блокчейн для оплаты товаров и услуг 
в рамках собственных проектов или даже осуществлять краудфандинг.

Not only that, but Waves tokens can also be used to pay fees within the network, creating additional 
demand for custom assets on its blockchain. After the initial creation of an asset, the total tokens supply can be further increased.

Выпуск токена на платформе Waves предоставляет некоторые преимущества, в том числе возможность мгновенно продать токен на
децентрализованном бирже. Также токены Waves могут использоваться для оплаты сборов в сети, создавая дополнительный спрос 
на пользовательские ассеты в его блокчейне. После первоначального создания ассета, общее количество токенов 
может быть дополнительно увеличено.

# 2. Операции над ассетами \(Issue, Reissue and Burn an Asset\) {#Assets(customtokens)-AssetsOperations(Issue,ReissueandBurnanAsset)}

Более подробную информацию об ассет-транзакциях можно найти [здесь](/development-and-api/waves-node-rest-api/asset-transactions.md).

## 2.1 Выпуск ассет-транзакции {#Assets(customtokens)-IssueAssetTransaction}

Эта транзакция ответственна за создание нового ассета, отвечающего специфическим запросам пользователя.

| Поле | Значение поля |
| :--- | :--- |
| Name | \[Имя ассета\] String \[4-16\] - идентификация ассета. Не обязано быть уникальным. |
| Details | \[Краткое описание ассета\] String \[0-1000\] - текстовое описание ассета. |
| Quantity | \[Общее количество токенов\] Long - количество выпущенных ассетов. Должны учитываться десятичные разряды, то 
есть количество умножается на число десятичных знаков на уровне API, чтобы иметь возможность работать только с целыми значениями.  |
| Reissuable | \[Возможность дополнительной выпуска, определяет, можно ли позднее довыпускать ассеты\]Boolean - флаг, определяющий
можно ли в дальнейшем довупустить этот ассет. |
| Decimals | Byte \[0-8\] - число десятичных знаков. |
| Issue Date | \[Дата создания ассета\]. |
| Fee | \[Комиссия за создание своего токена 1 WAVES\] Int - комиссия майнеров. |

## 2.2 Ассет-транзакция перевыпуска {#Assets(customtokens)-ReissueAssetTransaction}

Только человек, выпустивший ассет, имеет возможность перевыпустить ассет, если он нуждается в увеличении количества имеющихся ассетов.

| Поле | Значение поля |
| :--- | :--- |
| Issuer | \[Номер Waves адреса, который создал ассет\] Array\[Byte\] - txid транзакции выпуска. |
| Identifier | \[Идентификатор ассета. Уникальное значение, не может повторяться\] Array\[Byte\] - в случае перевыпуска ассета txid 
транзакции первого выпуска. |
| Quantity | \[Число дополнительно-выпускаемых ассетов\] Long. |
| Reissue Date | \[Дата создания перевыпуска\]. |
| Fee | \[Комиссия за создание своего токена 1 WAVES\] Int - комиссия майнеров. |

## 2.3 Сжигание ассетов {#Assets(customtokens)-BurnAsset}

Любой адрес, содержащий данный ассет, может решить уничтожить некоторые или все принадлежащие ему экземпляры ассета. Состояние ассета и списки 
пропусков пересчитываются на основе транзакции Delete.

| Поле | Значение поля |
| :--- | :--- |
| Issuer | \[Номер Waves адреса, с которого ассет был создан\] Array\[Byte\] - txid транзакции выпуска. |
| Quantity | \[Число сжигаемых ассетов\]. |
| Burn Date | \[Дата сжигания ассетов\]. |
| Fee | \[Комиссия за транзакцию\]. |

# 3. Примеры проверенных на данный момент ассетов {#Assets(customtokens)-HowtoIssueCustomizedTokenontheWavesPlatform}

* [Waves Community Token \(WCT\)](http://www.waveswiki.org/index.php?title=Waves_Community_Token_%28WCT%29)
* [Miner Reward Token \(MRT\)](http://www.waveswiki.org/index.php?title=Miner_Reward_Token_%28MRT%29)
* [Incent](http://www.waveswiki.org/index.php?title=Incent)
* [EncryptoTel \(ETT\)](http://www.waveswiki.org/index.php?title=EncryptoTel)
* [MobileGo Token \(Mgo\)](http://www.waveswiki.org/index.php?title=MobileGo_Token)
* [Wavesgo Token \(WGO\)](http://www.waveswiki.org/index.php?title=Wavesgo_Token)
* [Starrie \($STAR\)](http://www.waveswiki.org/index.php?title=Starrie)
* [Mercury \(MER\)](http://www.waveswiki.org/index.php?title=Mercury)
* [Riptobux \(RBX\)](http://www.waveswiki.org/index.php?title=Riptobux)
* [Wavesnode.NET \(WNET\)](http://www.waveswiki.org/index.php?title=Wavesnode.NET)

[Здесь](http://support.wavesplatform.com/forums/2-knowledge-base/topics/8141-list-of-verified-assets/) можно найти более полный, 
но не исчерпывающий список подтвержденных ассетов \(список постоянно обновляется\).

# 4. Пре-ICO продажа токенов на Waves DEX {#Assets(customtokens)-Pre-ICOTokenSaleonWavesDEX}

Чтобы организовать предпродажу токенов для вашего ICO на DEX необходимо сделать следующее:

1. Определить желаемое количество инвестиций. 
2. Установить цену за токен.
3. Выпустить серию ордеров на продажу.

Проданные токены будут автоматически доступны всем клиентам сразу после инвестирования в ваш проект.