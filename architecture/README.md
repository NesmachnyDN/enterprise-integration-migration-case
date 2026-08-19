# Архитектурные диаграммы

В каталоге находятся исходники Mermaid для ключевых представлений кейса. Они синтетические и не воспроизводят топологию, конфигурации или внутренние решения конкретной организации.

## Исходники

- `as-is.mmd` — исходный унаследованный интеграционный ландшафт;
- `transition.mmd` — переходная архитектура с временным сосуществованием двух платформ;
- `target.mmd` — целевая интеграционная архитектура;
- `migration-decision-tree.mmd` — классификация взаимодействия в один из сценариев M1–M4;
- `migration-factory.mmd` — повторяемый процесс миграции портфеля интеграций;
- `cutover-rollback.mmd` — переключение, проверка и откат.

## Визуальные версии

Готовые portfolio-grade SVG находятся в [`../assets/`](../assets/):

- [`architecture-as-is.svg`](../assets/architecture-as-is.svg);
- [`architecture-transition.svg`](../assets/architecture-transition.svg);
- [`architecture-target.svg`](../assets/architecture-target.svg);
- [`migration-decision-tree.svg`](../assets/migration-decision-tree.svg);
- [`migration-factory.svg`](../assets/migration-factory.svg);
- [`cutover-rollback.svg`](../assets/cutover-rollback.svg);
- [`enterprise-integration-migration-social-preview.svg`](../assets/enterprise-integration-migration-social-preview.svg) — обложка кейса.

## Принцип представления

Диаграммы намеренно показывают архитектурную логику, а не инфраструктурную детализацию. Порты, IP-адреса, реальные названия систем, учетные записи, команды, точные показатели нагрузки и эксплуатационные инструкции исключены.

Ключевое представление кейса — переходная архитектура: она показывает, как временный Compatibility Bridge позволяет независимо переводить участников интеграции с унаследованной транспортной платформы на целевую платформу и при этом имеет явные условия вывода из эксплуатации.
