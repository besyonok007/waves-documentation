# Upgrading Waves Node

Перед обновлением Ноды Waves проверьте используемый тип установки. Это может быть либо файл DEB (для всех Deb-base дистрибутивов GNU/Linux) или файл JAR (другие операционные системы). В зависимости от типа Ноды, выполните шаги одной из процедур приведённых ниже, чтобы обновить Ноду Waves. Подробное описание типов установки Нод Waves, можно найти в статьях [How to Install a Node](https://docs.wavesplatform.com/en/waves-node/how-to-install-a-node/how-to-install-a-node.html) и [How to Build and Test a Node](https://docs.wavesplatform.com/en/waves-node/how-to-build-and-test-a-node.html).

## Обновление JAR Ноды 

Чтобы обновить **JAR** Ноду, выполните следующие шаги:

1. Запустите Ноду, если она не запущена, выполнив следующую команду: 
```
java -jar waves.jar waves.conf
```
**Note:** Более подробно запуск Ноды описан в статье  [How to Install a Node](https://docs.wavesplatform.com/en/waves-node/how-to-install-a-node/how-to-install-a-node.html).

2. Проверьте версию установленной Ноды в файле **/var/log/waves/waves.log** или в названии **JAR** файла.
3. Проверьте актуальную версию Ноды на странице [latest Waves Release](https://github.com/wavesplatform/Waves/releases) и скачайте последнюю версию **Mainnet** релиза (**JAR** файл).
4. Изучите информацию о версии (release notes) на предмет необходимости повторной сборки базы данных состояния.
5. **При необходимости:** Если новая версия Ноды подразумевает повторную сборку базы данных состояния, экспортируйте существующие блоки.
Подробное описание экспорта/импорта блоков описано в статьях  [Export to the Blockchain](https://docs.wavesplatform.com/en/waves-node/options-for-getting-actual-blockchain/export-and-import-from-the-blockchain.html) и [State Downloading and Applying](https://docs.wavesplatform.com/en/waves-node/options-for-getting-actual-blockchain/state-downloading-and-applying.html).
     
   **Note:** импорт/экспорт блоков не является обязательным, но позволит сэкономить интернет-трафик, а иначе Нода загрузит все необходимые данные из сети.

6. Остановите Ноду (Остановите процесс java Waves).

7. Замените старый **JAR** файл новой скаченной версией.

8. При необходимости: Если новая версия Ноды подразумевает повторную сборку базы данных состояния, импортируйте бинарный файл. Подробное описание импорта блоков описано в статье [Import From the Blockchain](https://docs.wavesplatform.com/en/waves-node/options-for-getting-actual-blockchain/import-from-the-blockchain.html).
9. Запустите Ноду, выполнив следующую команду:
```
java -jar waves.jar waves.conf
```
## Обновление DEB Ноды

Чтобы обновить **DEB** Ноду, выполните следующие шаги:

1. Запустите Ноду, если она не запущена, выполнив следующую команду: 
```
# sudo systemctl start waves
```
**Note:** Более подробно запуск Ноды описан в статье [How to Install a Node](https://docs.wavesplatform.com/en/waves-node/how-to-install-a-node/how-to-install-a-node.html).

2. Проверьте версию установленной Ноды в файле **/var/log/waves/waves.log** или выполните следующую команду:
```
# dpkg -l waves
```
3. Проверьте актуальную версию Ноды на странице [latest Waves Release](https://github.com/wavesplatform/Waves/releases)и скачайте последнюю версию **Mainnet** релиза (**DEB** файл).
4. Изучите информацию о версии (release notes) на предмет необходимости повторной сборки базы данных состояния.
5. **При необходимости:** Если новая версия Ноды подразумевает повторную сборку базы данных состояния, экспортируйте существующие блоки.
Подробное описание экспорта/импорта блоков описано в статьях [Export to the Blockchain](https://docs.wavesplatform.com/en/waves-node/options-for-getting-actual-blockchain/export-and-import-from-the-blockchain.html) и [State Downloading and Applying](https://docs.wavesplatform.com/en/waves-node/options-for-getting-actual-blockchain/state-downloading-and-applying.html).
     
   **Note:** импорт/экспорт блоков не является обязательным, но позволит сэкономить интернет-трафик, а иначе Нода загрузит все необходимые данные из сети.
6. Остановите Ноду, выполнив следующую команду:

```
# sudo systemctl stop waves
```
7. Обновите существующий файл **DEB**, выполнив следующую команду:  

```
# sudo dpkg -i waves_X.Y.Z_all.deb
```
8. При необходимости: Если новая версия Ноды подразумевает повторную сборку базы данных состояния, импортируйте бинарный файл. Подробное описание импорта блоков описано в статье  [Import From the Blockchain](https://docs.wavesplatform.com/en/waves-node/options-for-getting-actual-blockchain/import-from-the-blockchain.html).
9. Запустите Ноду, выполнив следующую команду:
```
# sudo systemctl start waves
```
## Обновление Ноды через APT репозиторий

Ещё один и, пожалуй, самый удобный метод установки/обновления Ноды Waves на Linux это через APT репозиторий. Репозиторий содержит пакеты mainnet, testnet и stagenet.
При использовании данного метода, попутно автоматически загружаются сопутствующие файлы (а именно OpenJDK 8).

Чтобы установить новейшую версию Ноды mainnet через APT репозиторий, выполните следующие команды: 
```
curl -sL http://apt.wavesplatform.com/apt-key.gpg | sudo apt-key add -
sudo add-apt-repository "deb https://apt.wavesplatform.com/ xenial mainnet"
sudo apt update
sudo apt install waves
```
**Note:** Установочные пакеты Waves совместимы с версиями Linux Debian 8.0+, Ubuntu 16.04+ и их ответвлениями.

При выпуске новой версии Ноды Waves, можно обновить установленную Ноду, выполнив следующие команды: 

```
sudo apt update
sudo apt upgrade
```

## Обновление файла конфигурации Ноды

Подробное описание файла конфигурации Ноды содержится в статье [Waves node configuration file](https://docs.wavesplatform.com/en/waves-node/node-configuration.html).



