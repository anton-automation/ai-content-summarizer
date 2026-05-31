# AI Content Summarizer

Telegram-бот для автоматического анализа текстов с помощью GPT-4o-mini.

## Что делает

Принимает текст статьи → возвращает:
- краткое резюме
- 3 ключевых тезиса  
- категорию темы

## Архитектура

Telegram → IF (>100 символов) → OpenAI JSON mode → Edit Fields → Telegram
↓ false
"Пришли текст статьи"

## Стек

- n8n (Docker, localhost)
- OpenAI GPT-4o-mini
- Telegram Bot API

## Как запустить

1. Импортируй `ai_content_summarizer_v1.json` в n8n
2. Добавь credentials:
   - OpenAI API key
   - Telegram Bot token
3. Активируй workflow

## Демо

<img width="1557" height="735" alt="ai_content_summarizer" src="https://github.com/user-attachments/assets/bbfdbcf9-5054-4193-8e8c-8018bc542fa3" />


## Бизнес-ценность

Экономит 5–10 минут на каждой статье.
Подходит для: контент-маркетологов, SMM, медиа, аналитиков.
