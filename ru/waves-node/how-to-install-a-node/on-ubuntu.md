# Установка ноды на Ubuntu

Чтобы запустить ноду Waves, необходимо выполнить два шага:

1. Установить OpenJDK 8.
2. Загрузить файлы Waves и настроить приложение.

## Установка OpenJDK 8

Проверьте версию JDK с помощью консольной команды:

```
java -version
```

**Note:** Не устанавливайте OpenJDK 8 если у вас уже установлена версия OpenJDK 11. Приложение ноды поддерживает версии 8 и 11.

Установите OpenJDK 8, выполнив следующие команды:

```
sudo apt-get update
sudo apt-get install openjdk-8-jre
```

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

## Установка deb пакета на deb-based Linux (Ubuntu, Debian)

Загрузите последнюю версию deb пакета [Waves](https://github.com/wavesplatform/Waves/releases) и установите его с помощью команды: `sudo dpkg -i waves*.deb`.

Отредактируйте файл конфигурации Waves, который должен быть уже распакован из пакета deb  в папку: `/usr/share/waves/conf/waves.conf` (или `waves-testnet` для testnet) символическая ссылка `/etc/waves/waves.conf`. Внимательно изучите статью [Конфигурация ноды](/waves-node/node-configuration.md).

Есть два типа deb пакетов Waves: **upstart loader** и **systemd loader**.

### 1. Systemd (Ubuntu &gt;= 15.04):

Пользователи могут запустить ноду с помощью команды: `sudo systemctl start waves.service` (`waves-testnet` для testnet) и включить автозапуск при включении компьютера с помощью команды: `sudo systemctl enable waves.service`. **Systemd** Пользователи **Systemd** смогут найти логи journald приложения Waves с помощью команды:  `journalctl -u waves.service -f`. Подробно про journald [тут](https://www.digitalocean.com/community/tutorials/how-to-use-journalctl-to-view-and-manipulate-systemd-logs).

### 2. **Upstart (Ubuntu &lt; 15.04):**

Пользователи могут запустить ноду с помощью команды: `sudo service waves start` (`waves-testnet` для testnet) и включить автозапуск при включении компьютера с помощью команды: `sudo service waves enable`. Логи приложения Waves `/var/log/waves/waves.log`



**Чтобы поменять папку waves (для кошелька, блокчейна и других файлов ноды в пакетах ubuntu можно поменять, используя  **`-J-Dwaves.directory=path`** in **`/etc/waves/application.ini`**. Папка waves по умолчанию**`/var/lib/waves-testnet/`** задается в скрипте run systemd start.**

# Установка для продвинутых пользователей

Загрузите последнюю версию waves.jar пакета [Waves](https://github.com/wavesplatform/Waves/releases) и файл конфигурации .conf (для mainnet или testnet) в любую папку, например `/opt/waves`.

Отредактируйте файл конфигурации waves.conf, **это очень важно! От этого зависит безопасность вашего кошелька и средств!**

Откройте файл конфигурации своим любимым текстовым редактором, налейте в чашку вкусный чай и изучите статью [Конфигурация ноды](/waves-node/node-configuration.md)

Откройте консоль и перейдите в папку с файлом jar с помощью следующей команды: `cd /opt/waves` запустите ноду waves следующей командой: `java -jar waves.jar waves-config.conf`.

Now you can write a script to run every node, which you like and use it! I hope it's worth it! :\)

## Установка из исходников

* Добавьте в свой ~/.bashrc для увелиения памяти jvm:

  ```
  SBT_OPTS="-XX:MaxJavaStackTraceDepth=5000 -Xmx2536M -XX:+CMSClassUnloadingEnabled -Xss2M"
  ```

* Выполните в консоли:

  ```
  sudo apt install sbt
  ```

* Клонируйте репозиторий:

  ```
  git clone git@github.com:wavesplatform/Waves.git
  ```

* Запустите SBT в папке проекта:

  ```
  cd waves_project
  sbt
  packageAll
  ```

* Импортируйте проект в Intellij Idea

* Загрузите плагин для Intellij:

  * Scala

* Во время импорта проекта, выберите опцию:

  ```
  [x] Use sbt shell for build and import
  ```

* Увеличьте heap size до 2048 MB

* Настройте плагин "Scala Fmt"

# Дополнительная безопасность

Для дополнительной безопасности, рекомендуется хранить приложение кошелёк и файл конфигурации в зашифрованной разделе диска. Подробно об этом [тут](https://help.ubuntu.com/community/EncryptedFilesystems).

Также, возможно Вы захотите ограничить использование зашифрованных папок для некоторых пользователей. Подробно об этом [тут](http://manpages.ubuntu.com/manpages/precise/man1/chown.1.html). Скрипт deb пакета Waves создает пользователя. Приложение, кошелёк и папки с данными по умолчанию принадлежат ему данному пользователю.

Если Вы захотите использовать RPC, тогда необходимо защитить Ubuntu с помощью встроенного ufw или любого другого файервола. Подробно об этом [тут](https://www.digitalocean.com/community/tutorials/how-to-setup-a-firewall-with-ufw-on-an-ubuntu-and-debian-cloud-server). Если у Ваш сервер находится в публичном доступе и Вы захотите использовать RPC, тогда задействуйте только определённые методы, используя [Nginx's proxy\_pass module](http://nginx.org/ru/docs/http/ngx_http_proxy_module.html) и не забудьте назначить API key apiKeyHash хэш в файле конфигурации Waves.

Также, не забывайте своевременно обновлять операционную систему и программное обеспечение системы безопасности.