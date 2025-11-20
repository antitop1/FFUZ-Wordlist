# fuzz.txt — High-Quality Wordlist for Web Fuzzing

Этот репозиторий содержит оптимизированный словарь для фаззинга веб-приложений, предназначенный для инструментов вроде ffuf, Gobuster, Dirsearch, Feroxbuster и других.

Словарь `fuzz.txt` включает:
- современные пути и эндпоинты
- файлы конфигураций
- dev/backup/debug-файлы
- API-маршруты
- cloud / CI-CD / devops артефакты
- расширенные паттерны для поиска скрытых директорий и файлов

---

## Содержание репозитория
```
.
├── fuzz.txt        # Основной словарь
└── README.md       # Этот файл
```

---

## Назначение словаря
`fuzz.txt` подходит для:

- Директория-фаззинга
- Поиска скрытых файлов и конфигураций
- Сканирования API-эндпоинтов
- Поиска dev/backup/old/hidden ресурсов
- Ловли cloud-метадаты
- Docker/K8s артефактов
- CI/CD файлов

---

## Примеры использования
### ffuf
```bash
ffuf -u https://target.com/FUZZ -w fuzz.txt -mc 200,301,302,403
```

### gobuster
```bash
gobuster dir -u https://target.com -w fuzz.txt -x php,txt,html,js
```

### dirsearch
```bash
dirsearch -u https://target.com -w fuzz.txt -e php,js,txt,log
```

### feroxbuster
```bash
feroxbuster -u https://target.com -w fuzz.txt
```

---

## Качество словаря
Перед публикацией `fuzz.txt` был обработан:

- удаление дубликатов
- нормализация путей
- сортировка
- удаление пустых строк
- добавление современных паттернов
- включая API, cloud и devops-дороги

---

## Автоматизация
Скрипт для очистки словаря:

```bash
sort -u fuzz.txt -o fuzz.txt
```

Продвинутая версия на Python:
```python
with open("fuzz.txt") as f:
    items = {line.strip() for line in f if line.strip()}
with open("fuzz.txt", "w") as f:
    for i in sorted(items):
        f.write(i + "\n")
```

---

## Лицензия
Свободно используй, модифицируй и комбинируй.

---

## Поддержка
Если словарь полезен — поставь ★ и сделай форк.
Принимаются PR с новыми паттернами!

