# SSH


#### Директория /var/log . tail по умолчанию показывает последнии 10 строчек, а нам нужно 50.

```
tail -f -n50 /var/log/syslog
```

```
journalctl -xeu nginx
```
