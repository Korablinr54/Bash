# Менеджер пакетов apt

## Установка программ `apt install`

Для установки пакета программ используется приложение `apt`:
```sh
root@69b01309ee03:/# apt install terminator
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
```

### Проблема с установкой
При установке пакета может возникнуть ошибка. Ошибка `E: Unable to locate package terminator` означает, что пакетный менеджер APT не может найти пакет terminator в доступных репозиториях. Причин может быть несколько, мы попробуем обновить менеджер пакетов, в нашем случае это поможет.  
```sh
root@69b01309ee03:/# apt update
Get:1 http://archive.ubuntu.com/ubuntu noble InRelease [256 kB]
...
Get:18 http://archive.ubuntu.com/ubuntu noble-backports/universe amd64 Packages [33.9 kB]
Fetched 34.0 MB in 4s (7974 kB/s)
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
2 packages can be upgraded. Run 'apt list --upgradable' to see them.
```