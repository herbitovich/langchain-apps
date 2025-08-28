# LangChain Apps — набор ноутбуков для изучения LangChain

Набор Jupyter-ноутбуков для быстрых экспериментов с цепочками, агентами, RAG и семантическим поиском на базе **LangChain**.

> ✨ Основной упор — минимальные, воспроизводимые примеры без лишней магии.

---

## Содержание

* [Быстрый старт](#быстрый-старт)
* [Переменные окружения](#переменные-окружения)
* [Краткое описание ноутбуков](#краткое-описание-ноутбуков)
* [Планы/идеи](#планыидеи)
---

## Быстрый старт

1. **Python**: 3.10+ (рекомендуется 3.10–3.12).
2. **Создайте окружение** и поставьте зависимости:

```bash
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install jupyter ipykernel
python -m ipykernel install --user --name=langchain-apps

# Базовые пакеты LangChain
pip install "langchain>=0.3" "langchain-core>=0.3" "langchain-community>=0.3"

# Провайдер модели (пример: MistralAI)
pip install "langchain-mistralai" "python-dotenv"

```

3. **API‑ключи** положите в `.env` (см. ниже).
4. Откройте ноутбук: `jupyter notebook` → любой `*.ipynb`.

---

## Переменные окружения

Создайте файл `.env` в корне репозитория:

```env
# MistralAI (пример)
MISTRALAI_API_KEY=...
```

---

## Краткое описание ноутбуков

* **simple\_llm\_app.ipynb** — минимальный пайплайн: `MistralAI` + `PromptTemplate` + стриминг и параметры генерации.
* **structured\_output.ipynb** — получение **валидного JSON/TypedDict/Pydantic** через `with_structured_output(...)`, разбор и валидация.
* **semantic\_search\_engine.ipynb** — загрузка локальных файлов, разбиение на чанки, эмбеддинги, поиск по запросу.
* **rag\_pt1.ipynb** — подготовка данных для RAG: лоадеры (PDF/текст), сплиттеры, эмбеддинги, построение ретривера как ноды графа.
* **rag\_pt2.ipynb** — цепочка Retrieval‑Augmented Generation с использованием тулз семантик серча.
* **agent.ipynb** — простой агент с тулзами и обработка результата.
* **chatbot.ipynb** — чат‑цепочка с памятью.
* **writer.ipynb** — генератор статей/заметок: гайдлайны стиля, тема → поиск материала → план → написание. Обернут в телеграм бота.

> `Molmo.pdf` можно использовать как тестовый документ для RAG/поиска.

---

## Планы/идеи

* Добавить примеры с **Azure OpenAI / Anthropic / Google**.
* Показать RAG с **rerankers** и «source‑grounded» промптами.
* Мини‑демо **многошагового агента** на LangGraph.
* Нотбук с **эвалюацией** (точность/полезность/цитирование) и LangSmith‑трейсами.

PR‑ы и ишьюсы приветствуются 🙌

---
