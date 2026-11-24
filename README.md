# супер пупер мега турбо жиробас

Практическая работа по Git — задания **1.3, 2.6 и 2.7**. Тема: временное сохранение изменений, Reset и Revert.

**[Открыть полный отчёт с ответами на вопросы](REPORT.md)**

## Результаты работы

| Задание | Что выполнено | Результат | Материалы |
|---|---|---|---|
| 1.3 — Stash | Созданы `main.py`, `students.py`, ветка `feature-students`; выполнены `stash push -u` и `stash pop` | Изменения обоих файлов восстановлены, список stash пуст | [Код](exercises/01-stash) · [Команды](logs/01-stash.txt) |
| 2.6 — Reset Soft | Созданы две версии `app.py`, выполнен `reset --soft HEAD~1` | Ветка вернулась к первому коммиту, вторая версия осталась в индексе | [Код](exercises/02-reset-soft) · [Команды](logs/02-reset-soft.txt) |
| 2.6 — Reset Mixed | Эксперимент повторён в отдельном репозитории с `reset --mixed HEAD~1` | Ветка вернулась к первому коммиту, вторая версия осталась только в рабочем файле | [Код](exercises/02-reset-mixed) · [Команды](logs/02-reset-mixed.txt) |
| 2.7 — Revert | Созданы три коммита; последний отменён через `revert` | Появился четвёртый коммит; третий сохранён в истории, его изменение отменено | [Код](exercises/03-revert) · [Команды](logs/03-revert.txt) |

## Проверка

Повторная проверка выполнена после распаковки архива. Проверены целостность Git-объектов, содержимое файлов, история коммитов, индекс, список stash и совпадение архивных файлов с исходными. Все проверки прошли.

Состояния учебных репозиториев сохранены в **[готовом архиве](git-practice-1_3-2_6-2_7.zip)**. Он содержит четыре полных репозитория с историей Git, отчёт, ответы и вывод команд.

Обычная отправка ветки в GitHub не переносит незакоммиченные файлы, индекс и reflog. Поэтому точное итоговое состояние Stash и Reset сохранено в архиве, а итоговый код дополнительно доступен в папке [exercises](exercises).

## История упражнений

Исходные учебные коммиты сохранены в отдельных ветках без изменения их хешей. Ветки `before` показывают две версии до Reset, ветки `after` — положение ветки после Reset.

- [exercise/1-3-stash](https://github.com/promokoduzat-design/super-puper-mega-turbo-zhirobas/tree/exercise/1-3-stash)
- [exercise/2-6-soft-after](https://github.com/promokoduzat-design/super-puper-mega-turbo-zhirobas/tree/exercise/2-6-soft-after)
- [exercise/2-6-soft-before](https://github.com/promokoduzat-design/super-puper-mega-turbo-zhirobas/tree/exercise/2-6-soft-before)
- [exercise/2-6-mixed-after](https://github.com/promokoduzat-design/super-puper-mega-turbo-zhirobas/tree/exercise/2-6-mixed-after)
- [exercise/2-6-mixed-before](https://github.com/promokoduzat-design/super-puper-mega-turbo-zhirobas/tree/exercise/2-6-mixed-before)
- [exercise/2-7-revert](https://github.com/promokoduzat-design/super-puper-mega-turbo-zhirobas/tree/exercise/2-7-revert)

Ветка `main` содержит оформленную работу для просмотра. Ветка `exercise/2-7-revert` позволяет увидеть все четыре коммита Revert прямо на GitHub.

## Краткие ответы

- **Зачем нужен `stash -u`?** Чтобы включить новый неотслеживаемый файл `students.py`.
- **Почему после Soft изменения подготовлены?** `--soft` меняет указатель ветки, сохраняя индекс и рабочие файлы.
- **Чем отличается Mixed?** Он также сбрасывает индекс, но сохраняет рабочие файлы; изменения нужно снова добавить через `git add`.
- **Почему после Revert остался старый коммит?** Revert добавляет новый коммит с обратными изменениями, сохраняя предыдущую историю.

В учебных коммитах используется техническое имя `Student` и адрес `student@example.test`.
