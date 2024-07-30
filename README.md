# astra linux docker_docker-compose

### Шаг 1: Установка Docker

1. Обновите список пакетов и установите необходимые зависимости:

```
sudo apt-get update
sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common

```

2. Добавьте официальный GPG-ключ Docker:

```
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -

```

3. Добавьте репозиторий Docker в список источников APT:

```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"

```

4. Обновите список пакетов снова:

```
sudo apt-get update
```

5. Установите Docker CE:

```
sudo apt-get install docker-ce docker-ce-cli containerd.io

```
6. Проверьте установку Docker:

```
sudo systemctl status docker

```
### Шаг 2: Установка Docker Compose

1. Загрузите последнюю версию Docker Compose:

```
sudo curl -L "https://github.com/docker/compose/releases/download/$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep -Po '"tag_name": "\K.*\d')" /usr/local/bin/docker-compose

```
2. Сделайте файл исполняемым:

```
sudo chmod +x /usr/local/bin/docker-compose
```

3. Проверьте установку Docker Compose:

```
docker-compose --version
```

### Шаг 3: Настройка пользователя (опционально)

Чтобы использовать Docker без необходимости вводить sudo перед каждой командой, добавьте вашего пользователя в группу docker:

```
sudo usermod -aG docker $USER
```

Затем выйдите из системы и войдите снова, чтобы изменения вступили в силу.

### Заключение

Теперь у вас должны быть установлены Docker и Docker Compose на Astra Linux. Вы можете проверить их работу, запустив тестовые контейнеры или следуя инструкциям по настройке приложений с использованием Docker Compose, 
