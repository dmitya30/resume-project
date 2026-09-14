# n8n Data Table

Таблица создается пользователем вручную до импорта рабочего workflow.

Рекомендуемое имя таблицы:

```text
job_vacancies
```

## Поля

| Поле | Тип | Назначение |
|---|---|---|
| vacancy_id | String | Числовой идентификатор вакансии hh.ru. Логический уникальный ключ. |
| url | String | Канонический URL без аналитических параметров. |
| title | String | Название вакансии. |
| company | String | Название работодателя. |
| salary | String | Зарплата в исходном нормализованном представлении. |
| location | String | Регион или город. |
| work_format | String | Удаленная, офисная или гибридная работа. |
| experience | String | Требуемый опыт. |
| published_at | Date | Дата публикации, если извлечена. |
| first_seen_at | Date | Время первого обнаружения. |
| updated_at | Date | Время последнего изменения записи. |
| source_query | String | Имя поисковой конфигурации. |
| description_text | String | Очищенное описание вакансии. |
| content_hash | String | Хеш нормализованного содержимого. |
| status | String | Текущий статус обработки. |
| filter_reason | String | Причина отклонения жестким фильтром. |
| score | Number | Итоговая оценка соответствия. |
| recommended_resume | String | Рекомендованный вариант резюме. |
| analysis_json | String | Полный JSON результата оценки. |
| cover_letter | String | Подготовленное сопроводительное письмо. |
| telegram_message_id | String | ID сообщения Telegram, если оно отправлено. |
| last_error | String | Последняя диагностическая ошибка. |

Если конкретная версия n8n не поддерживает удобный тип Date, соответствующие значения можно временно хранить как ISO 8601 String.

## Статусы

```text
found
filtered
fetch_failed
parse_failed
scored
recommended
sent_to_telegram
applied_manually
rejected_manually
archived
error
```

## Правила

- Проверка дублей выполняется по vacancy_id.
- URL хранится без query-параметров.
- Уже обработанная вакансия не загружается повторно без отдельной причины.
- analysis_json хранится как сериализованная JSON-строка.
- last_error не должен содержать credentials, cookies или полные HTTP-заголовки.
- После создания таблицы ее фактическое имя нужно указать в workflow.
