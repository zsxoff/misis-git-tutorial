# MISIS Git Tutorial

## Установка и настройка Git

**Шаг 1.** Скачиваем и устанавливаем [cmder](https://cmder.net/), версию Full, включающую в себя клиент Git для Windows.

![](images/01.png)

**Шаг 2.** Создаем аккаунт на [GitHub](https://github.com/).

**Шаг 3.** Запускаем `cmder`.

Сначала настроим имя и e-mail для Git:

```bash
git config --global user.name "Konstantin Dobratulin"
git config --global user.email konstantin@example.com
```

Сгенерируем [SSH-ключ](https://ru.wikipedia.org/wiki/SSH) командой:

```bash
ssh-keygen -b 4096 -C konstantin@example.com
```

В ходе выполнения Вас попросят указать путь для сохранения файла (по умолчанию `C:\Users\YOURNAME\.ssh` - нажать Enter), затем - пароль и подтверждение пароля. Пароль не обязательно должен совпадать с паролем Git, можно указать любой. Он будет использоваться в дальнейшем при выполнении push на GitHub.

**Важно знать!** Вы генерируете два файла ключа - приватный (`id_rsa`) и публичный (`id_rsa.pub`). *Никогда не передавайте никому приватный файл `id_rsa`.*

![](images/cmder01.png)

Выведем ваш публичный ключ командой `cat C:\Users\YOURNAME\.ssh\id_rsa.pub`:

![](images/cmder02.png)

Затем, перейдем в настройки [SSH and GPG Keys](https://github.com/settings/keys) GitHub и добавим выведенный SSH-ключ, нажав на кнопку New SSH Key. В открывшееся окно вводим любое название ключа и копируем ключ из cmder:

![](images/cmder03.png)

---

**Шаг 4.** Заходим на страницу проекта [https://github.com/Kinetikm/misis_ida](https://github.com/Kinetikm/misis_ida), в правом верхнем углу жмем "Fork".

![](images/02.png)

Среди ваших проектов появится проект misis_ida с пометкой, что это форк другого репозитория.

![](images/03.png)

Жмем кнопку Code, выбираем Clone > SSH, копируем адрес из окошка.

![](images/04.png)

Переходим в cmder, перемещаемся в ваш каталог с проектами, например, командой `cd C:\Projects\Python`. Подойдет любой каталог, но лучше выбрать тот, в котором вы храните проекты, так как именно в него будет клонирован репозиторий с GitHub.

Вводим команду `git clone git@github.com:НИКНЕЙМ/misis_ida.git`. При первом клонировании вас спросят, хотите ли вы продолжить подключение, пишем `yes` и жмем Enter. Затем вводим ваш пароль от SSH с шага 3.

![](images/cmder04.png)

Вы великолепны! Выполните команду `cd .\misis_ida\` для перехода в каталог проекта и переходите к следующему шагу.
