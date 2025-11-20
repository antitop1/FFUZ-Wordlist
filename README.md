# fuzz_main.txt — High-Quality Wordlist for Web Fuzzing

Этот репозиторий содержит оптимизированный словарь для фаззинга веб-приложений, предназначенный для инструментов вроде ffuf, Gobuster, Dirsearch, Feroxbuster и других.

Словарь `fuzz_main.txt` включает:
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
├── fuzz_main.txt        # Основной словарь
└── README.md       # Этот файл
```

---

## Назначение словаря
`fuzz_main.txt` подходит для:

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
ffuf -u https://target.com/FUZZ -w fuzz_main.txt -mc 200,301,302,403
```

### gobuster
```bash
gobuster dir -u https://target.com -w fuzz_main.txt -x php,txt,html,js
```

### dirsearch
```bash
dirsearch -u https://target.com -w fuzz_main.txt -e php,js,txt,log
```

### feroxbuster
```bash
feroxbuster -u https://target.com -w fuzz_main.txt
```

---

## Лицензия
Свободно используй, модифицируй и комбинируй.

---

## Поддержка
Если словарь полезен — поставь ★ и сделай форк.
Принимаются PR с новыми паттернами!

SEO: web fuzzing wordlist, ffuf wordlist, Gobuster dictionary, Dirsearch fuzz list, Feroxbuster optimized wordlist, API fuzzing, backup file detection, cloud metadata wordlist, CI/CD fuzzing, pentest wordlist.

