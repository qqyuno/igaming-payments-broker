# Provider scorecard

Обновлено: 2026-07-30.

## Назначение

Scorecard нужен, чтобы отличать реального подходящего партнёра от компании,
которая только заявляет о работе с high-risk или iGaming. Оценка проводится
до merchant outreach и обновляется после каждого разговора или реального кейса.

Публичная страница, affiliate program или устное обещание не заменяют проверку
юридического лица, acceptance policy и письменных коммерческих условий.

## Статусы

- **Research** — найдена компания, проверка не завершена.
- **Contacted** — отправлен запрос партнёрскому или sales-контакту.
- **Qualified** — подтверждены базовые eligibility criteria.
- **Terms received** — условия и lead-registration process получены письменно.
- **Active** — пригоден для конкретного сегмента и готов принимать introductions.
- **Paused** — есть блокирующий вопрос или слабая отчётность.
- **Rejected** — не проходит обязательные критерии.

## Обязательные фильтры

Провайдер автоматически получает **Rejected** или **Paused**, если не подтверждён
хотя бы один критический пункт:

- проверяемое юридическое лицо и официальный домен;
- понятный регулируемый статус там, где он требуется;
- явное разрешение работать с заявленным типом licensed iGaming;
- список принимаемых лицензий и запрещённых географий;
- отсутствие предложения скрывать MCC, домены, GEO или бенефициаров;
- стандартный KYB/KYC и underwriting process;
- письменный порядок регистрации referral lead;
- письменная формула комиссии и событие выплаты;
- официальный договор или иное юридически значимое подтверждение условий;
- отсутствие запроса передать полный контакт мерчанта до защиты атрибуции.

## Взвешенная оценка

Оценка каждого блока — от 0 до 5. Итог рассчитывается как сумма
`score / 5 × weight`.

| Блок | Вес | Что проверяется |
|---|---:|---|
| Legal and compliance | 20 | Юрлицо, лицензии, KYB, iGaming policy, restricted GEOs |
| Product and coverage | 20 | Методы, валюты, GEOs, pay-in/payout, product fit |
| Underwriting fit | 15 | Принимаемые лицензии, объёмы, processing history, risk appetite |
| Commercial terms | 15 | Referral event, ставка, duration, tail, clawback |
| Attribution and reporting | 10 | Lead registration, dashboard/reports, volume visibility |
| Settlement and funds risk | 10 | Settlement, reserve, hold, safeguarding, payout reliability |
| Integration and support | 5 | API, webhooks, sandbox, docs, technical owner |
| Reputation and execution | 5 | Track record, references, responsiveness, rejection clarity |

Интерпретация:

- **80–100** — кандидат на Active после получения письменных условий;
- **65–79** — использовать только для узкого подтверждённого use case;
- **50–64** — Paused до устранения пробелов;
- **ниже 50** — Rejected;
- провал обязательного фильтра нельзя компенсировать высоким общим баллом.

## Карточка провайдера

Для каждого кандидата фиксировать:

### Identity

- Provider name:
- Website:
- Legal entity:
- Registration country:
- Regulator/licence, если применимо:
- Проверено по первичному источнику и дата:
- Main contact, role, public source:

### Product

- Category: PSP / acquirer / APM / crypto gateway / dispute / orchestration:
- Pay-in methods:
- Payout methods:
- Settlement currencies:
- Supported countries:
- Restricted countries:
- Accepted gambling licences:
- Prohibited products или business models:

### Underwriting

- Minimum monthly volume:
- Maximum or preferred volume:
- Processing history required:
- Required company age:
- Required documents:
- Expected underwriting timeline:
- Typical reasons for rejection:
- Можно ли провести предварительную анонимизированную проверку профиля:

### Pricing and funds

- Setup/integration fee:
- Processing pricing:
- FX/settlement fees:
- Rolling reserve:
- Fixed reserve:
- Settlement delay:
- Hold/freeze conditions:
- Chargeback/dispute fees:

Цены фиксируются только как подтверждённые или ориентировочные с датой и
источником. Они не обещаются мерчанту от имени провайдера.

### Integration

- API documentation:
- Sandbox:
- Webhooks:
- Hosted checkout/API integration:
- Supported platforms:
- Technical support model:
- Integration owner and escalation path:

### Partner terms

- Agreement received:
- Lead-registration method:
- Lead acceptance confirmation:
- Commission event:
- Referral fee или revenue-share formula:
- Revenue-share duration:
- Post-termination tail:
- Reporting method:
- Payout schedule:
- Minimum payout:
- Payout currencies:
- Clawback:
- Related brands/entities treatment:
- Existing-account and duplicate-lead rules:

### Evidence and status

- Primary sources:
- Written confirmations:
- Open questions:
- Score:
- Status:
- Owner:
- Last verified:
- Next action and date:

## Вопросы на первом партнёрском разговоре

1. Какие gambling licences и player GEOs вы принимаете сегодня?
2. Какие iGaming-профили вы точно не рассматриваете?
3. Какой monthly volume и processing history вам нужен?
4. Можете ли вы дать acceptance matrix письменно?
5. Как регистрируется лид и когда считается защищённым?
6. Какое событие запускает referral fee или revenue share?
7. Как партнёр проверяет объём и начисленную комиссию?
8. Что происходит с комиссией после прекращения договора?
9. Какие reserve, hold и settlement terms типичны для этого профиля?
10. Кто принимает решение по предварительной квалификации и underwriting?
11. Как устроен технический handoff и кто отвечает за интеграцию?
12. В какой валюте и по каким документам выплачивается комиссия?

## Правила передачи лида

До передачи контакта:

1. Получить минимальную квалификацию оператора.
2. Отправить провайдеру обезличенный профиль, если процесс это допускает.
3. Получить подтверждение fit и правила регистрации.
4. Зарегистрировать юридическое лицо, бренд и домен.
5. Получить письменное подтверждение атрибуции.
6. Получить согласие оператора на introduction.
7. Провести знакомство с обеими сторонами в одном письме или чате.
8. Зафиксировать следующего владельца действия и дату follow-up.

Не передавать KYC-файлы, персональные документы или закрытые финансовые данные
через репозиторий. Они должны передаваться напрямую по согласованному защищённому
каналу между оператором и провайдером.

## Минимум для начала merchant outreach

Outreach разрешён, когда есть минимум два провайдера со статусом **Active** и:

- разным coverage или дополняющими продуктами;
- письменной acceptance matrix;
- понятной процедурой lead registration;
- подтверждённой формулой комиссии;
- рабочим контактом для pre-check и escalation;
- отсутствием критических compliance red flags.
