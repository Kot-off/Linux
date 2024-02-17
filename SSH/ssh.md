# SSH

### Создаём ключ на master

```
ssh-keygen -t ed25519
```

### Заходим на worker, создаём директорию и файл

```
cd ~ && mkdir .ssh
```

### В данный файл нужно перекинуть публичный ключ с master-a

```
nano authorized_keys
```

### Выставляем права

```
chown -R $USER:$USER ~/.ssh
chmod 700 ~/.ssh
chmod 644 ~/.ssh/*
chmod 600 ~/.ssh/id_* ~/.ssh/authorized_keys
```

### Устанавливаем openssh-server

```
sudo apt-get install -y openssh-server
```

### Далее потребуется зайти в config и раскомментировать следующие параметры.

```
cd /etc/ssh/ssh_config
```

- Port 22
- PubkeyAuthentication yes
- AuthorizedKeysFile .ssh/authorized_keys

### Перезапускаем SHH

```
systemctl restart ssh
```
