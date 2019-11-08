# Экспорт блокчейна
![master](https://img.shields.io/badge/node->%3D0.8.0-4bc51d.svg)

Если у Вас уже есть нода Waves синхронизированная с правильным блокчейном, Вы можете экспортировать данные блокчейна.

## Экспорт существующих блоков в бинарный файл

Перед началом экспорта блоков, необходимо остановить ноду. Для экспорта существующих блоков в бинарный файл, выполните следующую команду. Экспорт это довольно быстрый процесс, но полученный бинарный файл может дополнительно занять до 1/3 пространства `data` папки с данными.

You have to stop the node before starting export of blocks. To export existing blockchain to the binary file run following command. Export is quite a fast operation, but resulting binary file could additionally take up to 1/3 of  folder size on disk.

_**В Windows:**_

```
java -cp waves-all-<version>.jar com.wavesplatform.Exporter -c [configuration-file-name] -o [output-file-name] -h [height]
```

_**В Linux:**_

```
Mainnet: sudo -u waves waves export -c /etc/waves/waves.conf -o [output-file-name] -h [height]
Testnet: sudo -u waves-testnet waves-testnet export -c /etc/waves-testnet/waves.conf -o [output-file-name] -h [height]
```
Если параметр `height` не задан, будут экспортированы все блоки. В другом случае будут экспортированы только блоки до заданного значения `height`.

Имя файла экспорта - не обязательный параметр, имя 'blockchain' используется по умолчанию. В результате экспорта, файл с именем '<output-file-name>-<height>' будет создан в текущей папке.

## Удалить данные существующей ноды

Для того, чтобы полностью пересобрать ноду, необходимо удалить `data` папку с существующими данными ноды.

В Windows, `data` папка обычно расположена в: `%HOMEPATH%\waves\data`.

В Linux: `/var/lib/waves[-testnet]/` folder:

```
sudo rm -rdf /var/lib/waves[-testnet]/data
```

## Загрузить экспортируемый блокчейн

Загрузить недавно экспортированный блокчейн можно по следующим ссылкам:

{% prettylink link="http://blockchain.wavesnodes.com/" %}MainNet{% endprettylink %}

{% prettylink link="http://blockchain.testnet.wavesnodes.com/" %}TestNet{% endprettylink %}



