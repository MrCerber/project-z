# Руководство по работе с Claude Code

---

## Основной принцип

Ты — архитектор. Claude Code — твоя команда.
Claude Code не принимает архитектурные решения, не определяет направление продукта и не решает вопросы безопасности самостоятельно — это всегда твоя зона ответственности.

---

## Стек инструментов

### Шаг 1 — Методология

**BMAD Method** — обязателен для большого проекта.
Ведёт от идеи до реализации со специализированными агентами по фазам.

```bash
npx bmad-method install
```

Процесс BMAD для большого проекта (Level 3-4):
```
/workflow-init    → инициализация проекта
/product-brief    → Фаза 1: формирование идеи
/prd              → Фаза 2: детальные требования
/architecture     → Фаза 3: проектирование системы
/sprint-planning  → Фаза 4: планирование спринта
/dev-story        → Фаза 4: реализация истории
```

---

### Шаг 2 — Память

**MemPalace** — обязателен для длинного проекта.
Сохраняет каждый разговор дословно. Claude Code помнит всё между сессиями.

```bash
claude plugin marketplace add milla-jovovich/mempalace
claude plugin install --scope user mempalace
/mempalace:init
```

---

### Шаг 3 — Экономия токенов

**Caveman** — экономит 75% токенов, сохраняя полную техническую точность.

```bash
claude plugin marketplace add JuliusBrussee/caveman
claude plugin install caveman@caveman
```

---

### Шаг 4 — Качество и методология

**Superpowers** — TDD, отладка, автоматическая верификация.

```bash
/plugin install superpowers@claude-plugins-official
```

---

### Шаг 5 — Multi-Agent (только когда готов)

⚠️ Не начинать с этого с первого дня. Сжигает токены очень быстро.

```bash
# Включение agent teams
# settings.json:
{ "env": { "CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS": "1" } }

# Оркестратор
claude plugin marketplace add barkain/claude-code-workflow-orchestration
claude plugin install workflow-orchestrator@barkain-plugins
```

---

## CLAUDE.md — самое важное

**Правила:**
- До 200 строк — каждая строка должна зарабатывать своё место
- Обновляется после каждого исправления — чтобы одна и та же ошибка не повторялась
- Содержит: архитектуру, соглашения, команды, что нельзя трогать

```bash
/init  # создаёт CLAUDE.md автоматически из кодовой базы
```

---

## Ежедневный рабочий процесс

```
1. /mempalace:wake-up     — загрузка контекста
2. /workflow-status        — где остановился
3. BMAD направляет задачу
4. /plan для каждой задачи >3 шагов
5. Claude Code реализует
6. Superpowers обеспечивает качество
7. MemPalace сохраняет всё
```

---

## Золотые правила

```
✅ Plan mode для каждой задачи более 3 шагов
✅ Короткая сфокусированная сессия — не одна длинная
✅ Каждое исправление → новое правило в CLAUDE.md
✅ Полный spec до первой строки кода
✅ Tests до implementation (TDD)

❌ CLAUDE.md более 200 строк
❌ Multi-agent с первого дня
❌ Ожидать что Claude сам примет архитектурные решения
❌ Давать размытый промпт и ожидать готовый продукт
❌ Одна длинная сессия вместо нескольких коротких
```

---

## Модели

```
Plan mode  → Opus (глубокое мышление)
Coding     → Sonnet (быстро и эффективно)
/model     → смена модели внутри сессии
```

---

## Рекомендуемые MCP серверы

```bash
# GitHub — управление repo напрямую
/plugin add github-mcp

# PostgreSQL — работа с БД
/plugin add postgres-mcp
```

---

*Обновлено 19.04.2026*
