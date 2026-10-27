# ub-mode
Локальная копия [unclebob/ub-mode](https://github.com/unclebob/ub-mode). Принципы те же. В разделе **Then Make it Right** проверки crapper, dryer и mutator заменены на Pest, PHPStan и Pint.
`ub-mode` задаёт порядок работы при любом изменении кода. Основа — сокращённые правила [@poteto](https://github.com/poteto) (`poteto-mode` / `pstack`).
1. **First Make it Work** — Laziness Protocol, Foundational Thinking, TDD, Redesign From First Principles, Attack the Premise, Subtract Before You Add, Outcome-Oriented Execution, Build the Lever и Architecture (Model the Domain, Boundary Discipline, Type System Discipline, Make Operations Idempotent, Separate Before Serializing Shared State).
2. **Then Make it Right** — Fix Root Causes, Sequence Work into Verifiable Units, Test Behavior (Not Implementation), Pest, PHPStan, Pint и Refactoring.
3. **Practice** — Keep a Log, Guard the Context Window, Worktree Cleanup, Commit and Push небольшими упорядоченными коммитами.
## Проверки PHP
Запускать команды так, как это уже делает проект. Если PHP в проекте выполняется только в Docker, все три команды идут внутри этого контейнера.
| Проверка | Что обязана показать | Чем запускать |
| --- | --- | --- |
| Pest | Тесты на изменённое поведение. Тест, который проходит, если каждая функция ничего не возвращает, не считается. | Команда тестов проекта (обычно `php artisan test`). |
| PHPStan | Уровень, уже настроенный в проекте. Замечание в затронутом коде не заглушается. Причина исправляется. Код, который анализатор показывает как неиспользуемый, удаляется. | Команда PHPStan проекта. |
| Pint | Изменённые файлы в стиле, который проект уже принимает. | `vendor/bin/pint`, если бинарник есть. Если его нет и стиль гоняет php-cs-fixer, эта проверка — `composer cs-fix`. |

## Installation

Copy `SKILL.md` into your agent's skills directory as `ub-mode/SKILL.md` (for example `~/.grok/skills/ub-mode/SKILL.md`, `~/.claude/skills/ub-mode/SKILL.md`, or `~/.cursor/skills/ub-mode/SKILL.md`), then invoke `/ub-mode`.
