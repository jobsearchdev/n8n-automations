# n8n Automations — SEO

Автоматизації в [n8n](https://n8n.io/) для SEO-команди: пришвидшення індексації сторінок у пошукових системах і збір позицій сайту в Google. Створені та використовувались у роботі; тут опубліковано очищені версії без ключів і даних клієнтів.

*English version below.*

| # | Автоматизація | Що робить | Сервіси |
|---|---|---|---|
| 01 | [Indexing — URL list](workflows/01-indexing-urllist) | Приймає список URL через webhook і відправляє їх у сервіс пришвидшеної індексації | Webhook, HTTP API, webhook.site |
| 02 | [Indexing — sitemaps monitor](workflows/02-indexing-sitemaps) | Кожні 15 хв сканує sitemap.xml, знаходить нові й оновлені сторінки (за `lastmod`) і відправляє на індексацію лише їх | Schedule, XML, JavaScript, n8n Data Tables, HTTP API, Telegram |
| 03 | [SERP positions → Google Sheets](workflows/03-serp-positions) | Збирає позиції сторінок у видачі Google за ключовим словом і записує в Google Sheets. На основі цього флоу зробили сервіс збору позицій | DataForSEO API, Google Sheets |

## Як імпортувати

1. n8n → **Workflows → Import from File** → вибери `workflow.json` потрібної автоматизації.
2. Заміни всі значення `YOUR_...` на свої (API-ключі, ID таблиць, домен n8n, Telegram chat ID).
3. Підключи credentials у вузлах Google Sheets і Telegram.
4. Запусти вручну на тестових даних, потім активуй workflow.

## Безпека

Ключі, логіни, ID таблиць, адреси вебхуків і домени клієнтів замінено на заглушки `YOUR_...` та `example.com`. Не зберігай справжні ключі прямо в полях вузлів — краще використовуй n8n Credentials.

---

## English

[n8n](https://n8n.io/) automations built for an SEO team: speeding up page indexing in search engines and collecting Google rankings. They were used in production; this repository contains sanitized versions without keys or client data.

| # | Automation | What it does | Services |
|---|---|---|---|
| 01 | [Indexing — URL list](workflows/01-indexing-urllist) | Accepts a list of URLs via webhook and submits them to a fast-indexing service | Webhook, HTTP API, webhook.site |
| 02 | [Indexing — sitemaps monitor](workflows/02-indexing-sitemaps) | Every 15 minutes scans sitemap.xml files, detects new and updated pages (by `lastmod`) and submits only those for indexing | Schedule, XML, JavaScript, n8n Data Tables, HTTP API, Telegram |
| 03 | [SERP positions → Google Sheets](workflows/03-serp-positions) | Collects Google organic rankings for a keyword and writes them to Google Sheets. A rank-tracking service was built on top of this flow | DataForSEO API, Google Sheets |

**Import:** n8n → Workflows → Import from File → `workflow.json`, then replace every `YOUR_...` placeholder and connect credentials.

**Security:** keys, logins, sheet IDs, webhook URLs and client domains were replaced with `YOUR_...` placeholders and `example.com`.
