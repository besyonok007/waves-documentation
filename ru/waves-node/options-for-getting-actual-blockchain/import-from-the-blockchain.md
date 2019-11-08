# Импорт из блокчейна
![master](https://img.shields.io/badge/node->%3D0.8.0-4bc51d.svg)

Если у вас уже есть синхронизированная нода Waves, вы можете импортировать данные блокчейн. Импорт можно использовать для ускорения процесса получения данных блокчейн.

## Импорт блоков из бинарного файла

Ноду необходимо остановить перед импортом блокчейна. Если в папке `data` ноды уже есть какие-то данные, процедура импорта продолжит получение данных из бинарного файла блокчейна. Лучше всего удалить существующие данные, потому что смешивание данных из разных версий может вызвать ошибки.

Для импорта блокчейна и сборки состояния, выполните следующую команду (Импорт это тяжелая операция, выполнение которой может занять до нескольких часов):

### В Windows

```bash
java -cp waves-all-<version>.jar com.wavesplatform.Importer -c [configuration-file-name] -i [binary-file-name]
```

### В Linux

```bash
Mainnet: sudo -u waves waves import -c /etc/waves/waves.conf -i [binary-file-name]

Testnet: sudo -u waves-testnet waves-testnet import -c /etc/waves-testnet/waves.conf -i [binary-file-name]
```

## Импорт блоков до определённой "высоты"

Можно задать целевую "высоту". Если параметр `height` не задан, будут импортированы все блоки. Для импорта, выполните команду:

### В Windows

```
java com.wavesplatform.Importer -c <config_file> -i <blockchain_file> -h <height>
```

### В Linux

```
Mainnet: sudo -u waves waves import -c /etc/waves/waves.conf -i /path/to/mainnet-1234688
Testnet: sudo -u waves-testnet waves-testnet import -c /etc/waves-testnet/waves.conf -i /path/to/testnet-1234688
```
