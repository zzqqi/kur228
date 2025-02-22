# Самсонов Сергей К-ИСП-39-2
Ввел команду `sudo yum install wget` 

Что бы скачать файл


![image](https://github.com/user-attachments/assets/470210ff-f6a1-485b-9870-8076262d8d78)

Так как вылезла ошибка делаю следующее:


Ввел команду `su root`

что бы зайти в cmd от имени администратора, потом ввел команду `vi /ect/sudoers`

и производим изменения 


![image](https://github.com/user-attachments/assets/8aedc754-4535-4888-a4ff-52924e34641c)

Дал права пользователю **kuromi**

Опять вписал команду `sudo yum install wget`

 что бы скачать пакет `wget`

_Эта утилита предназначена для загрузки файлов из интернета._

Установил пакет **wget-1.21.1-8.el9_4.x86_64**



![image](https://github.com/user-attachments/assets/5d6eb098-534a-4932-a2a1-8e3a06a24707)


 Ввел команду  `sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo`
 Команда скачивает конфигурационный файл для репозитория Docker в CentOS.

![image](https://github.com/user-attachments/assets/d54df09d-dc93-4dce-a82b-81d92b8d4711)

Ввел команду `sudo yum install docker-ce docker-ce-cli containerd.io`           Она используется для установки пакетов, необходимых для работы Docker

![image](https://github.com/user-attachments/assets/3f753696-edeb-47de-a7f6-24345acb0533)

Команда     `sudo systemctl enable docker --now`      запускает службу Docker и настраивает её автоматический запуск при загрузке системы.

![image](https://github.com/user-attachments/assets/d725d402-3b7f-4a99-809b-1effcc5babc8)


Ввел команду     `COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)`       используется для определения последней версии docker-compose и команду      `sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose`          для скачивания скрипта Docker Compose с Github и помещения его в каталог /usr/bin.

![image](https://github.com/user-attachments/assets/7b632eeb-7369-480e-99a4-d48cad4c1bac)

 Ввел команды
 
`sudo chmod +x /usr/bin/docker-compose`             _добавляет загруженному бинарному файлу Docker Compose права на выполнение._

`docker-compose --version`                       _для проверки корректности работы утилиты_

![image](https://github.com/user-attachments/assets/d597f334-8f3c-4edb-8e5f-013cbe3603d0)


`git clone https://github.com/skl256/grafana_stack_for_docker.git`               _она клонирует репозиторий grafana_stack_for_docker с GitHub_

![image](https://github.com/user-attachments/assets/2f58b247-7683-4838-a1aa-16546293b577)


`cd grafana_stack_for_docker`                _перемещает в директорию grafana_stack_for_docker, которая была создана при клонировании репозитория_
`sudo mkdir -p /mnt/common_volume/swarm/grafana/config`           _создает директорию config по пути /mnt/common_volume/swarm/grafana/_
`sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data}`            _создает три директории: grafana-config, grafana-data и prometheus-data в директории /mnt/common_volume/grafana/_

![image](https://github.com/user-attachments/assets/9e69d355-2b70-4463-85ac-e4f33996975f)


`sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}`          _изменяет владельца и группу для всех файлов и директорий_
`touch /mnt/common_volume/grafana/grafana-config/grafana.ini`                       _создает пустой файл с именем grafana.ini_

![image](https://github.com/user-attachments/assets/64ed4c57-2203-4c37-9ab7-5760c7c8e287)



`cp config/* /mnt/common_volume/swarm/grafana/config/`             _копирует все файлы из директории config_

`mv grafana.yaml docker-compose.yaml`                      _переименовывает файл grafana.yaml в docker-compose.yaml в текущей директории_

![image](https://github.com/user-attachments/assets/478111d4-870b-400d-b2b8-2fa2d163ea90)

`sudo docker compose up -d`
         _Docker Compose создаст и запустит все контейнеры, указанные в файле docker-compose.yaml, в фоновом режиме._


![image](https://github.com/user-attachments/assets/9c2cbafe-25eb-4f18-87fc-361a5616a6c2)


![image](https://github.com/user-attachments/assets/4c1741fa-9327-44f5-90dc-f09d1728b7f6)


`ls`         используется для просмотра содержимого директории
`Cd grafana_stack_for_docker/`           _изменяет текущую директорию на grafana_stack_for_docker_
`Ls`          _снова отображает список файлов и директорий, но теперь уже в директории grafana_stack_for_docker_
`vi docker-compose.yaml`         _открывает файл docker-compose.yaml в текстовом редакторе vi_

![image](https://github.com/user-attachments/assets/3bf080f5-0832-4dcb-ab6d-9f0768bc8743)

`sudo docker-compose stop`         _останавливает запущенные контейнеры, которые были созданы с помощью Docker Compose_

![image](https://github.com/user-attachments/assets/21e05e83-3835-4b48-a0ae-583b5d6e88ef)

`sudo docker-compose up -d`             _создает и запускает контейнеры в фоновом режиме_

![image](https://github.com/user-attachments/assets/a5a88a9d-27ca-4e9c-88a2-5da145ca2bd9)

`sudo docker-compose down`        _останавливает и удаляет все контейнеры, сети и тома, созданные с помощью docker-compose up_

![image](https://github.com/user-attachments/assets/79ca7fa6-d378-41ac-9035-3f6a048d9845)

`sudo docker-compose up -d`         _снова создает и запускает контейнеры в фоновом режиме, как описано ранее_

![image](https://github.com/user-attachments/assets/612b7b65-9ec8-497e-8acf-7f6ecbb471f9)

`sudo docker-compose ps`        _отображает список контейнеров, которые управляются Docker Compose, и их текущее состояние_

![image](https://github.com/user-attachments/assets/98111f50-2bf6-4585-9c9d-542beb9d7195)
