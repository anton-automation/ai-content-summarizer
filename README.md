# AI Content Summarizer

Telegram-бот для автоматического анализа текстов с помощью GPT-4o-mini.

## Что делает

Принимает текст статьи → возвращает:
- краткое резюме
- 3 ключевых тезиса  
- категорию темы
- логирование каждого запроса в Google Sheets (timestamp, текст, резюме, категория)
- команда /history — показывает последние 5 анализов
- /start — приветствие и инструкция
- /help — список команд  
- /history — последние 5 анализов

## Архитектура

```
Telegram → IF_router (команды) → /start, /help, /history
         → IF (>100 символов) → OpenAI JSON mode → Edit Fields → Telegram
                ↓ false
         "Пришли текст статьи"
```

## Стек

- n8n (Docker, localhost)
- OpenAI GPT-4o-mini
- Telegram Bot API
- Google Sheets API (Service Account)

## Как запустить

1. Импортируй `ai_content_summarizer_v1.json` в n8n
2. Добавь credentials:
   - OpenAI API key
   - Telegram Bot token
   - Google Sheets Service Account
3. Дай доступ Service Account к таблице
4. Активируй workflow

## Демо

![ai_content_summarizer](screenshots/ai_content_summarizer.png)

## Версии

### v1 (текущая)
- JSON mode — структурированный вывод
- Команды /start, /help, /history
- Google Sheets логирование
- IF роутинг команд через Switch node

## Бизнес-ценность

Экономит 5–10 минут на каждой статье.
Подходит для: контент-маркетологов, SMM, медиа, аналитиков.
