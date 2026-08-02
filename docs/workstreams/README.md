# Работа с двух устройств

Обновлено: 2026-08-02.

## Зачем это нужно

Два чата работают параллельно, но не должны менять одну и ту же стратегию или
перезаписывать результаты друг друга. `main` остаётся единственным источником
подтверждённых решений, а каждый чат ведёт свой рабочий поток в отдельном файле
и короткой Git-ветке.

## Распределение ответственности

| Поток | Главная задача | Рабочий файл | Результат текущего этапа |
|---|---|---|---|
| Provider Side | Найти и квалифицировать реальных партнёров | [`provider-side.md`](provider-side.md) | 2 провайдера Active с письменными условиями |
| Merchant Side | Подготовить ICP, triggers, сообщения и discovery | [`merchant-side.md`](merchant-side.md) | Готовность запустить один узкий merchant-сегмент после provider gate |

Provider Side определяет фактическое coverage. Merchant Side не выбирает GEO,
лицензию или продукт окончательно, пока не получена acceptance matrix минимум
двух провайдеров.

## Provider gate

Системный merchant outreach разрешён только когда одновременно выполнено:

- минимум два провайдера имеют статус **Active**;
- acceptance matrix получена письменно;
- подтверждены commercial terms и commission event;
- существует защищённая lead-registration procedure;
- провайдеры дают различающееся или дополняющее coverage;
- нет критических compliance red flags.

До этого Merchant Side занимается только подготовкой материалов и desk research.

## Владение файлами

### Provider Side может менять

- `docs/workstreams/provider-side.md`;
- `docs/provider-scorecard.md`, если уточняется методика оценки;
- новые обезличенные шаблоны для provider research.

### Merchant Side может менять

- `docs/workstreams/merchant-side.md`;
- новые шаблоны qualification, outreach и discovery;
- обезличенные результаты проверки сообщений.

### Общие файлы

`README.md`, `AGENTS.md`, `docs/session-handoff.md`, `docs/decision-log.md`,
`docs/project-context.md`, `docs/go-to-market-strategy.md` и
`docs/30-day-validation-plan.md` меняются только в отдельной integration-сессии
после объединения рабочих веток. Если рабочему потоку нужно общее изменение, он
записывает предложение в своём файле в блоке «Запросы на интеграцию».

## Git-процесс для каждого чата

В начале задачи:

```text
git switch main
git pull --ff-only
git switch -c work/provider-YYYYMMDD-topic
```

Для Merchant Side используется префикс `work/merchant-YYYYMMDD-topic`.

В конце задачи:

```text
git status --short
git diff --check
git add <только файлы своего потока>
git commit -m "research: ..."  # или docs:/experiment:
git push -u origin <имя-ветки>
```

После проверки ветка объединяется в `main`. Перед следующей задачей всегда
выполняется новый `git pull --ff-only`; старые рабочие ветки не используются
повторно.

## Integration-сессия

После завершения заметного результата одного или обоих потоков один чат:

1. убеждается, что обе нужные ветки объединены;
2. обновляет числа и единый следующий шаг в `docs/session-handoff.md`;
3. переносит только принятые стратегические решения в `docs/decision-log.md`;
4. снимает выполненные запросы на интеграцию из файлов потоков;
5. делает отдельный атомарный commit с префиксом `docs:`.

Integration-сессию не запускают одновременно на двух устройствах.

## Что нельзя хранить в публичном репозитории

- персональные email, телефоны и закрытые контакты;
- договоры, pricing sheets и непубличные acceptance matrices;
- KYC/KYB-файлы, банковские реквизиты, API-ключи и пароли;
- внутренние данные работодателя, клиентов или провайдеров;
- полный lead pipeline с персональными данными.

В Git фиксируются шаблоны, обезличенные выводы, публичные источники, агрегированные
числа и статусы. Рабочий pipeline и закрытые условия ведутся в приватном хранилище.

## Стартовые сообщения для двух чатов

### Чат Provider Side

> Ты отвечаешь только за Provider Side. Прочитай AGENTS.md, README.md,
> docs/session-handoff.md, docs/workstreams/README.md,
> docs/workstreams/provider-side.md и docs/provider-scorecard.md. Работай в
> короткой ветке `work/provider-*`. Не запускай merchant outreach и не меняй
> общие стратегические файлы; предложения записывай в «Запросы на интеграцию».

### Чат Merchant Side

> Ты отвечаешь только за Merchant Side. Прочитай AGENTS.md, README.md,
> docs/session-handoff.md, docs/workstreams/README.md,
> docs/workstreams/merchant-side.md и docs/go-to-market-strategy.md. Работай в
> короткой ветке `work/merchant-*`. До прохождения provider gate готовь ICP,
> triggers, qualification и outreach assets, но ничего не отправляй без моего
> прямого разрешения.
