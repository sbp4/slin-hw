# Домашнее задание к занятию "3.2 Управление пакетами"

---

### Кейс 1.

Опишите плюсы работы с пакетным менеджером и репозиторием. 

* Как вы считаете, в чем основные достоинства такой организации ПО? 
* Есть ли минусы?

*Напишите ответ в свободной форме.*

***Ответ:***

1. Достоинство работы с пакетным менеджером заключается в том, что он позволяет установить в систему уже откомпилированную программу, готовую к работе. В Linux данная программа назвается пакет. По сути, это архив специального формата, который содержит все необходимые приложению бинарные и конфигурационные файлы. Кроме этого, информацию о том, как их следует разместить в файловой системе, данные о зависимостях пакета, а также список действий которые необходимо выполнить в процессе установки. Благодаря информации, хранимой в пакете, пакетный менеджер может обновлять, обрабатывать зависимости, доустанавливать необходимые дополнительные пакеты, а также удалять все компоненты программы. Большинство пакетов хранятся в репозиториях, которые автоматически настраиваются в процессе установки.

2. На мой взгляд, минус можно выделить следующий. Не все программы можно найти в стандартных репозиториях. Некоторые разработчики выкладывают свои программные продукты в собственные репозитории. Соответственно, для установки нужной программы необходимо прописать сторонний репозиторий, а также скачать pgp-ключ репозитория для проверки подлинности устанавливваемых файлов.

---

### Кейс 2.

При подключении стороннего репозитория надо выполнить ряд определенных действий.

* Каких?
* В чем опасность такого способа распространения ПО?
* Как это решается?

*Напишите ответ в свободной форме.*

***Ответ:***

1. Для подключения стороннего репозитория нужно: 
   - скачать необходимое ПО: apt-transport-https, lsb-release, ca-certificates
   - указать репозиторий в source.list пакетного менеджера 
   - скачать pgp-ключ репозитория

2. В таких репозиториях может распространяться вредоносное ПО

3. Решается данная проблема следующим образом: выбираются репозитории, содержащие pgp-ключ и установавливается антивирусное ПО.

---

### Кейс 3.

#### Перейдем к практике. 

1. Запустите свою виртуальную машину.
2. Найдите в репозиториях и установите одной командой пакет `htop`.

Какие зависимости требует `htop`?

*Ответ приведите в виде текста команды, которой вы это выполнили, а также приложите скриншот места расположения исполняемых файлов установленного ПО.*

***Ответ:***

1. Поиск и установка пакета `htop`
sudo apt search htop | grep htop && sudo apt -f install -y htop

2. Проверка зависимостей `htop`
sudo apt show htop

<a href="https://ibb.co/0CQFZbB"><img src="https://i.ibb.co/sKt6QY5/3-2.png" alt="3-2" border="0"></a>

3. Место расположения исполняемых файлов установленного ПО:
which htop

<a href="https://ibb.co/TrKg0CF"><img src="https://i.ibb.co/hCXmdqt/3-3.png" alt="3-3" border="0"></a>

---

### Кейс 4.

1. Подключите репозиторий PHP и установите PHP 7.4.

*Приложите скриншот содержимого файла, в котором записан адрес репозитория.*

2. При помощи команды `php -v` убедитесь, что бы поставлена корректная версия PHP. 

*Приложите к ответу скриншот версии.*

***Ответ:***

1. Файл php.list

<a href="https://ibb.co/ZhZ1MVL"><img src="https://i.ibb.co/8jh470K/4-1.png" alt="4-1" border="0"></a>

2. Версия PHP:

<a href="https://ibb.co/XDTZ3Nj"><img src="https://i.ibb.co/G9jvtBn/4-2.png" alt="4-2" border="0"></a>

---

### Кейс 5.

Ваш коллега-программист просит Вас установить модуль `google-api-python-client` на сервер, который необходим для программы, работающей с Google API. 

Установите данный пакет при помощи менеджера пакетов `pip`. 

**Примечение №1:** для установки может быть необходим пакет `python-distutils`, проверьте его наличие в системе. 

**Примечение №2:** не забудьте выдать права на исполение скачанному файлу. Возможно, будет ошибка при установки при помощи Python версии 2, в таком случае воспользйтесь командой `python3`.

*Приложите скриншоты  с установленным пакетом `python-distutils`, с версией `Pip` и установленными модулями (должны быть видимы)*

***Ответ:***

1. Установленный пакет `python-distutils`:

<a href="https://ibb.co/HhQnvgj"><img src="https://i.ibb.co/jJFgK4S/5-1.png" alt="5-1" border="0"></a>

2. Версия `Pip`:

<a href="https://ibb.co/Bw8nNfT"><img src="https://i.ibb.co/1bHz60R/5-2.png" alt="5-2" border="0"></a>

3. Установленные модули:

<a href="https://ibb.co/kDQnXLP"><img src="https://i.ibb.co/Jp5LHYS/5-3.png" alt="5-3" border="0"></a>

---

**

## Дополнительные задания (со звездочкой*)
Эти задания дополнительные (не обязательные к выполнению) и никак не повлияют на получение вами зачета по этому домашнему заданию. Вы можете их выполнить, если хотите глубже и/или шире разобраться в материале.

### Кейс 6.

1. Перечислите менеджеры пакетов, кроме тех, о которых говорилось на лекции. 
В каких дистрибутивах они работают?

2. Есть ли альтернативные менеджеры для тех, которые разбирались на лекции?

*Напишите ответ в свободной форме.*

***Ответ:***

1. wajig, aptitude - Debian; zypper - SuSe Linux; pacman - Arch, Manjaro; portage, emerge - Gentoo; dnf, flatpack - Fedora; appgrid - Ubuntu; synaptic - Debian, Ubuntu; Gnome Software, flatpack, snap - могут использоваться и в .deb, и в .rpm системах.

2. aptitude, synaptic, Gnome Software, flatpack, snap  могут работать как альтернатива apt; dnf, Gnome Software, flatpack, snap могут работать как альтернатива yum. Не знаю, насколько корректно будет это обощение, но предположу, что все пакетные менеджеры, работающие в .deb системах могут быть взаимозаменяемы. Точно так же и как пакетные менеджеры для .rpm систем, тоже могут быть взаимозаменяемы. Все зависит от предпочтения.

---

### Кейс 7.

1. Скачайте исходники любого приложения и соберите пакет для того дистрибутива, на котором вы работаете.
2. Установите его при помощи менеджера пакетов

*Ответ приведите в виде скриншота.*

***Ответ:***

1. Компиляция и установка пакета:

<a href="https://ibb.co/Ct1PV3B"><img src="https://i.ibb.co/9v8Zykn/7-1.png" alt="7-1" border="0"></a>

2. Информаци по установленному пакету:

<a href="https://ibb.co/fkfSVkm"><img src="https://i.ibb.co/rxYtKxn/7-2.png" alt="7-2" border="0"></a>

3. Bashtop:

<a href="https://ibb.co/TTfXRFQ"><img src="https://i.ibb.co/W3h9FYr/7-3.png" alt="7-3" border="0"></a>
