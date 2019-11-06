# Installing a node on Windows

Чтобы запустить ноду Waves, необходимо выполнить два шага:

1. Установить OpenJDK 8.
2. Загрузить файлы Waves и настроить приложение.

## Установка OpenJDK 8

Проверьте версию JDK с помощью консольной команды:

```
java -version
```

**Note:** Не устанавливайте OpenJDK 8 если у вас уже установлена версия OpenJDK 11. Приложение ноды поддерживает версии 8 и 11.

Загрузите и усановите [OpenJDK 8](https://access.redhat.com/documentation/en-us/openjdk/8/html/openjdk_8_for_windows_getting_started_guide/getting_started_with_openjdk_for_windows).

Проверьте версию JDK с помощью команды:

```
java -version
```

Если Вы видите следующий результат, то переходите к следующему шагу:

```
java version "1.8.0_201"
Java(TM) SE Runtime Environment (build 1.8.0_201-b09)
Java HotSpot(TM) 64-Bit Server VM (build 25.201-b09, mixed mode)
```

## Загрузка пакета Waves и настройка приложения

[Загрузите последнюю версию](https://github.com/wavesplatform/Waves/releases) waves.jar и обязательного .conf файла конфигурации (для mainnet или testnet) в любую папку, например `~/waves`.

Отредактируйте файл конфигурации waves.conf, **это очень важно! От этого зависит безопасность вашего кошелька и средств!**

Откройте файл конфигурации своим любимым текстовым редактором, налейте вкусный чай в чашку и изучите статью  [Конфигурация ноды](/waves-node/node-configuration.md).

Запустите командную строку Windows, перейдите в папку с файлом jar с помощью команды `cd C:/waves` и запустите ноду следующей командой: `java -jar waves.jar waves.conf`.

## Дополнительная безопасность

Для дополнительной безопасности, рекомендуется хранить приложение кошелёк и файл конфигурации в зашифрованной разделе диска. Можно использовать, например, [BitLocker](https://technet.microsoft.com/en-us/library/cc731549%28v=ws.10%29.aspx), [TrueCrypt](http://truecrypt.sourceforge.net/), [AxCrypt](http://www.axcrypt.net/), [DiskCryptor](https://diskcryptor.net/), [FreeOTFE](https://sourceforge.net/projects/freeotfe.mirror/), [GostCrypt](https://www.gostcrypt.org/), [VeraCrypt](https://veracrypt.codeplex.com/) и пр. **Выбирайте приложение на свой страх и риск!**

Также, возможно Вы захотите ограничить использование зашифрованных папок для некоторых пользователей. Подробно об этом [тут](https://technet.microsoft.com/en-us/library/cc754344%28v=ws.11%29.aspx).

Если Вы захотите использовать RPC, тогда необходимо защитить Windows с помощью встроенного или любого другого файервола. Подробно об этом [тут](http://www.howtogeek.com/112564/how-to-create-advanced-firewall-rules-in-the-windows-firewall/). Если Ваш сервер находится в публичном доступе и Вы захотите использовать RPC, тогда задействуйте только определённые методы, используя [Nginx's proxy\_pass module](http://nginx.org/ru/docs/http/ngx_http_proxy_module.html) и не забудьте назначить API key хэш в файле конфигурации Waves.

Также, не забывайте своевременно обновлять операционную систему и программное обеспечение системы безопасности.
