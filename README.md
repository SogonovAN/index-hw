# Домашнее задание к занятию "Система мониторинга Zabbix" - `Согонов Алексей`

### Задание 1


![Название скриншота 1](https://github.com/SogonovAN/Zabbix-hw/blob/main/1.JPG)`


---

### Задание 2


stages:
  - test
  - build

test:
  stage: test
  image: golang:1.17
  script: 
   - go test .

build:
  stage: build
  image: docker:latest
  script:
   - docker build .


![Название скриншота 2](https://github.com/SogonovAN/gitlab-hw/blob/main/2.1.JPG)`

![Название скриншота 3](https://github.com/SogonovAN/gitlab-hw/blob/main/2.2.JPG)`

