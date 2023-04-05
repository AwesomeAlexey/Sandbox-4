# #FollowMe
___

## Add ssh keys
1. Записывам ключ в файл в директории /home/$user/.ssh
2. Убеждаемся, что разрешено только чтение-запись файла от имени пользователя
   - `sudo chmod 600 $file`

### Connect to the server
Подключаемся `ssh tester@ip`
   - Если не даёт доступ - указываем файл ключа `ssh -i ~/.ssh/$file tester@ip`

### Configure ssh keys for github, add to github
1. Выполняем `ssh-keygen` - генерируем пару ключей
2. Оставляем имя по умолчанию, пароль можно не задавать
3. Публичный ключ выводим при помощи функции `cat ~/.ssh/id_rsa.pub`
4. Копируем публичный ключ (Ctrl + Shift + C)
5. Идём в GitHub:
   - Настройки -> SSH and GPG keys
   - нажимаем на `New SSH key` в верхнем правом углу
   - В поле `key` вставляем скопированный ранее публичный ключ, даём произвольное название
6. Подтверждаем добавление ключа при помощи пароля или push-уведомления на телефоне

### git clone
Плашка `<> Code` в правом верхнем углу интерфейса, вкладка SSH, копируем строку
Скачиваем репозиторий решения при помощи `git clone url`. url в формате `git@github.com:$github_username/$repo_name.git`


### Prepare env, prepare test
Заходим в папку с решением, выполняем сначала подготовку середы, а затем подготовку тестов

Выполняем:
```
   ./prepare_env.sh
   ./prepare_test.sh
```


### If you wanna commit - git config email, name

### Tester case
```
    git fetch origin scripts:scripts
    git checkout scripts
```

### Run tests

В обычном случае - ручками запускаем run.sh скрипты
Как вариант - запускать скрипты пачками из папки scripts в репозитории 
(не стал кидать в папку тестов, раз там нам это не нужно).

Хардкорный вариант - ./sprint1.sh && ./sprint2.sh && ./sprint3.sh && ./sprint4.sh
