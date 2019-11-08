## Загрузка и актуализация состояния

В данном случае пользователю необходимо загрузить [_**latest State**_](http://blockchain.wavesnodes.com) или актуальное состояние блоков, **blockchain\_last.tar**_ \(это база данных, которая генерируется когда нода получает новые блоки\).  
Обратите внимание, что этот файл регулярно обновляется. В целом, **State** представляет собой **LevelDB** базу данных, файлы которой хранятся в папке `/var/lib/waves/data`

### Пошаговая инструкция

Для загрузки файлов состояния и актуализации базы, выполните следующие шаги:

1. Загрузите базу данных состояния (файл blockchain_last.tar) по ссылке [Download](http://blockchain.wavesnodes.com).
2. Запустите checksum с помощью какого-нибудь инструмента, чтобы проверить оба файла из ссылки выше (checksum файла **blockchain_last.tar** должен быть таким же как значение в данном файле: _**blockchain_last.tar.SHA1SUM**).
3. Удалите папку с данными, выполнив следующую команду: `sudo rm -rdf /var/lib/waves/data`
4. Распакуйте файлы базы данных состояния в папку: `/var/lib/waves/data`.
5. Запустите ноду, выполнив следующую команду: `sudo systemctl start waves`

Недавно экспортированные базы данных можно скачать по следующим ссылкам:

* TestNet: [http://blockchain.testnet.wavesnodes.com/](http://blockchain.testnet.wavesnodes.com/)
* MainNet: [http://blockchain.wavesnodes.com/](http://blockchain.wavesnodes.com/)



