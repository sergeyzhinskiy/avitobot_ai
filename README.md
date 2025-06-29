# avitobot_ai
ai bot sales assistant for Avito

Telegram bot for sales with Avito and YandexGPT integration

[![Python 3.8](https://img.shields.io/badge/Python-3.8-blue.svg)](https://www.python.org/downloads/release/python-380/)
[![Windows 7](https://img.shields.io/badge/OS-Windows%207-green.svg)](https://support.microsoft.com/ru-ru/windows/windows-7)

A bot for automating sales via Telegram and Avito using YandexGPT. Can provide product consultations, process orders, and learn from your data.

🔥 Features
- Consultations on products via Telegram and Avito
- Auto-responses based on FAQ and sales scripts
- Parsing products from Excel and web pages
- Placing orders with manager notification
- Training on your data (prices, scripts, chat logs)

⚙️ Installation
1. Requirements
- Windows 7 (or higher)
- Python 3.8
- Accounts:
- [Yandex Cloud](https://cloud.yandex.ru/) (for GPT)
- [Avito API](https://developers.avito.ru/) (for chats)
- Telegram bot via [@BotFather](https://t.me/BotFather)

2. Setup
1. Clone the repository:
```bash
#git clone https://github.com/your_repo/sales_bot.git
cd sales_bot
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Create a `.env` file in the root:
```ini
TELEGRAM_TOKEN=your_bot_token
YANDEX_API_KEY=your_yandex_cloud_api_key
YANDEX_FOLDER_ID=catalog_id
AVITO_TOKEN=avito_api_token
MANAGER_CHAT_ID=manager_chat_id
```

📚 Knowledge Base
Data is stored in JSON/Excel:
- Products: `data/products.json` (or downloadable Excel files)
- Scripts: `data/scripts.json`
- FAQ: `data/faq.json`

File formats
1. Excel price list (example):
| id | name | price | description |
|-----|--------------|---------|-------------------|
| 101 | TV | 29990 | Diagonal 55" |

2. Scripts (JSON):
```json
{
"greeting": "Good afternoon! How can I help you?",
"discount": "Special offer: 10% discount today!"
}
```

3. FAQ (JSON):
```json
{
"How to pay?": "By card or cash on delivery",
"Is there delivery?": "Yes, all over Russia"
}
```

🚀 Launch
```bash
python main.py
```

Note: For Windows 7, use PowerShell or CMD.

🛠️ Commands for administration
| Command | Description | Example |
|--------------------------|-----------------------------------|---------------------------|
| `/load_price` + file | Upload Excel price list | `/load_price` (attach file) |
| `/add_script name "text"` | Add script | `/add_script discount "Promotion 20%!"` |
| `/add_faq "Question?" "Answer"` | Add a question to FAQ | `/add_faq "Warranty?" "2 years"` |
| `/get_unknown_questions` | Show unanswered questions | — |

🔍 Examples of work
1. Dialogue in Telegram
```
Buyer: Do you have laptops for up to 50,000?
Bot: I recommend Acer Aspire 5 for 49,990 rubles (specifications...)
Buyer: Order for me
Bot: Specify a phone number for contact?
[Manager receives a notification]
```

2. Chat on Avito
```
Buyer: Is this product in stock?
Bot (via Avito API): Yes, delivery tomorrow!
```

3. Bot training
```
Admin: /add_faq "Is there an installment plan?" "Yes, 0% on 6 months"
Bot: ✅ Question added to FAQ!
```

📊 Logging
Logs are saved in `sales_bot.log`:
```log
2023-11-25 14:23:56 - bot_core - INFO - New order #ORD-20231125-142356
2023-11-25 14:24:01 - avito_manager - ERROR - Avito API error: timeout
```

⚠️ Limitations
- Windows 7 requires manual installation of Python 3.8.
- Avito API may limit the request rate (max. 1 request/sec).
- YandexGPT has a limit of 1000 requests/day (free plan).

📌 Support
For setup questions:
- Email: sergeyzhinskiy@gmail.com
- Telegram: @Russkayamednayakompaniya

Author: sergeyzhinskiy
Version: 1.0.0
=========================================================

AI бот-помощник по продажам для Avito

Telegram-бот для продаж с интеграцией Avito и YandexGPT

[![Python 3.8](https://img.shields.io/badge/Python-3.8-blue.svg)](https://www.python.org/downloads/release/python-380/)
[![Windows 7](https://img.shields.io/badge/OS-Windows%207-green.svg)](https://support.microsoft.com/ru-ru/windows/windows-7)

Бот для автоматизации продаж через Telegram и Avito с использованием YandexGPT. Умеет консультировать по товарам, обрабатывать заказы и обучаться на ваших данных.

🔥 Возможности
- Консультации по товарам через Telegram и Avito
- Автоответы на основе FAQ и скриптов продаж
- Парсинг товаров из Excel и веб-страниц
- Оформление заказов с уведомлением менеджера
- Обучение на ваших данных (прайсы, скрипты, логи чатов)


⚙️ Установка
1. Требования
- Windows 7 (или выше)
- Python 3.8
- Аккаунты:
  - [Yandex Cloud](https://cloud.yandex.ru/) (для GPT)
  - [Avito API](https://developers.avito.ru/) (для чатов)
  - Telegram-бот через [@BotFather](https://t.me/BotFather)

2. Настройка
1. Склонируйте репозиторий:
   ```bash
   #git clone https://github.com/your_repo/sales_bot.git
   cd sales_bot
   ```

2. Установите зависимости:
   ```bash
   pip install -r requirements.txt
   ```

3. Создайте файл `.env` в корне:
   ```ini
   TELEGRAM_TOKEN=ваш_токен_бота
   YANDEX_API_KEY=ваш_yandex_cloud_api_key
   YANDEX_FOLDER_ID=идентификатор_каталога
   AVITO_TOKEN=токен_api_avito
   MANAGER_CHAT_ID=id_чата_менеджера
   ```


📚 База знаний
Данные хранятся в JSON/Excel:
- Товары: `data/products.json` (или загружаемые Excel-файлы)
- Скрипты: `data/scripts.json`
- FAQ: `data/faq.json`

Форматы файлов
1. Excel-прайс (пример):
   | id  | name          | price  | description       |
   |-----|---------------|--------|-------------------|
   | 101 | Телевизор     | 29990  | Диагональ 55"     |

2. Скрипты (JSON):
   ```json
   {
     "приветствие": "Добрый день! Чем могу помочь?",
     "скидка": "Спецпредложение: скидка 10% сегодня!"
   }
   ```

3. FAQ (JSON):
   ```json
   {
     "Как оплатить?": "Картой или наличными при получении",
     "Есть доставка?": "Да, по всей России"
   }
   ```


🚀 Запуск
```bash
python main.py
```

Примечание: Для Windows 7 используйте PowerShell или CMD.


🛠️ Команды для администрирования
| Команда                  | Описание                          | Пример                     |
|--------------------------|-----------------------------------|----------------------------|
| `/load_price` + файл     | Загрузить Excel-прайс            | `/load_price` (прикрепить файл) |
| `/add_script название "текст"` | Добавить скрипт          | `/add_script скидка "Акция 20%!"` |
| `/add_faq "Вопрос?" "Ответ"` | Добавить вопрос в FAQ    | `/add_faq "Гарантия?" "2 года"` |
| `/get_unknown_questions` | Показать неотвеченные вопросы    | —                          |


🔍 Примеры работы
1. Диалог в Telegram
```
Покупатель: Есть ноутбуки до 50000?
Бот: Рекомендую Acer Aspire 5 за 49990 руб. (характеристики...)
Покупатель: Закажите мне
Бот: Укажите телефон для связи?
[Менеджер получает уведомление]
```

2. Чат на Avito
```
Покупатель: Этот товар в наличии?
Бот (через Avito API): Да, доставка завтра!
```

3. Обучение бота
```
Админ: /add_faq "Есть рассрочка?" "Да, 0% на 6 месяцев"
Бот: ✅ Вопрос добавлен в FAQ!
```


📊 Логирование
Логи сохраняются в `sales_bot.log`:
```log
2023-11-25 14:23:56 - bot_core - INFO - Новый заказ #ORD-20231125-142356
2023-11-25 14:24:01 - avito_manager - ERROR - Ошибка API Avito: timeout
```

⚠️ Ограничения
- Для Windows 7 требуется ручная установка Python 3.8.
- Avito API может ограничивать частоту запросов (макс. 1 запрос/сек).
- YandexGPT имеет лимит в 1000 запросов/день (бесплатный тариф).


📌 Поддержка
По вопросам настройки:
- Email: sergeyzhinskiy@gmail.com
- Telegram: @Russkayamednayakompaniya



Автор: sergeyzhinskiy 
Версия: 1.0.0
