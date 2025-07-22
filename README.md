# Домашнее задание к занятию "`GitLab`" - `Егоров Дмитрий`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

Задание 1
Что нужно сделать:

Разверните GitLab локально, используя Vagrantfile и инструкцию, описанные в этом репозитории.
Создайте новый проект и пустой репозиторий в нём.
Зарегистрируйте gitlab-runner для этого проекта и запустите его в режиме Docker. Раннер можно регистрировать и запускать на той же виртуальной машине, на которой запущен GitLab.
В качестве ответа в репозиторий шаблона с решением добавьте скриншоты с настройками раннера в проекте.

`Gitlab установлен`
<img width="1403" height="903" alt="image" src="https://github.com/user-attachments/assets/4933042c-5ab8-4b17-86e2-0a4eb4986886" />
`Создал новый проект и пустой репозиторий в нём`
<img width="1566" height="926" alt="image" src="https://github.com/user-attachments/assets/dc7ac4be-bf84-47ea-b58e-bc974a2d92eb" />
`Зарегистрировал gitlab-runner заупстил в Docker`
<img width="1168" height="845" alt="image" src="https://github.com/user-attachments/assets/53b12bf1-0dec-4e79-9769-548189885af1" />
`Настройки раннера`
<img width="1626" height="930" alt="image" src="https://github.com/user-attachments/assets/aca7f79c-57c2-4cac-8bc5-8bd07779b0e9" />

---

Задание 2
Что нужно сделать:

Запушьте репозиторий на GitLab, изменив origin. Это изучалось на занятии по Git.
Создайте .gitlab-ci.yml, описав в нём все необходимые, на ваш взгляд, этапы.
В качестве ответа в шаблон с решением добавьте:

файл gitlab-ci.yml для своего проекта или вставьте код в соответствующее поле в шаблоне;
скриншоты с успешно собранными сборками.




1. `Я перенес файл с Гитхаба к себе локально на ВМ и затес запушил в http://gitlab.localdomain/root/git10`
<img width="1426" height="317" alt="image" src="https://github.com/user-attachments/assets/c67a51c7-f7d6-41f4-a7a3-8d2a36ec8b59" />
2. `Изменил название на git10`
<img width="1614" height="931" alt="image" src="https://github.com/user-attachments/assets/8d8bb871-1aa2-4caf-aa20-ac2484b44940" />

файл .gitlab-ci.yml
```
stages:
  - test
  - build

test:
  stage: test
  image: golang:1.17
  script:
   - go test .
  tags:
    - netology

build:
  stage: build
  image: docker:latest
  script:
   - docker build .
  tags:
    - netologyПоле для вставки кода...

```
`Я написал код pipeline и он рабочий, но единственное так как у меня gitlab поднят локально на ВМ с Линукс то GitLab Runner не может подключиться к Docker Registry, так как у меня GitLab сидит на айпишнике 192.168.56.10 ( а Vagrant у меня не получилось поднять так как haspicorp заблочили в России)`
<img width="1590" height="906" alt="image" src="https://github.com/user-attachments/assets/98687c79-5c90-42ac-aaa9-d363d58ee054" />
<img width="1622" height="926" alt="image" src="https://github.com/user-attachments/assets/b7bd31c4-4420-4e10-85cb-fcecece6c305" />




