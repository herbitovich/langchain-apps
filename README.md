# LangChain Apps — набор ноутбуков для изучения LangChain

Набор Jupyter-ноутбуков для быстрых экспериментов с цепочками, агентами, RAG и семантическим поиском на базе **LangChain**.

---

## Сетап

1. Python: 3.10+.
2. Создайте окружение и поставьте зависимости:

```bash
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install jupyter ipykernel
python -m ipykernel install --user --name=langchain-apps
pip install "langchain>=0.3" "langchain-core>=0.3" "langchain-community>=0.3" "python-dotenv"

# Провайдер модели (здесь Mistral)
pip install "langchain-mistralai"

```

3. Заполните `.env` соответствующим API-ключом.

---

## Переменные окружения

`.env` в корне репозитория для Mistral:

```env
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
