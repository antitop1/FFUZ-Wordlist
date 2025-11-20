# Web Fuzzing Wordlists

Коллекция специализированных словарей для фаззинга веб-приложений с помощью **ffuf**, **DirBuster** и аналогичных инструментов. Словари содержат актуальные паттерны файлов и директорий, собранные из реальных проектов.

## Содержание

- `wordlists/`
  - `common-files.txt` – Популярные файлы конфигурации, точки входа, скрытые файлы
  - `dotfiles.txt` – Файлы, начинающиеся с точки (включая системные и инструментальные)
  - `env-patterns.txt` – Варианты файлов окружения (.env, config и т.д.)

## Пример содержимого
.env.example
main/.env
docs/.env
client/.env
.env.dev
blogs/.env
shared/.env
download/.env
.env.php
site/.env
sites/.env
web/.env
.bower-registry
.bower-tmp
.bower.json
.buckconfig
.build/
.buildpacks
.buildpath
.buildpath/
.builds
.bundle
.bundle/
.busted
.byebug_history
.bz2


## Использование

### С FFUF
ffuf -w wordlists/common-files.txt -u https://target/FUZZ
ffuf -w wordlists/dotfiles.txt -u https://target/.FUZZ

С DirBuster/Gobuster
gobuster dir -w wordlists/common-files.txt -u https://target.com/
dirb https://target.com/ wordlists/env-patterns.txt
