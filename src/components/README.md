# Компоненты

## Универсальные (base)

Их можно использовать в любом месте приложения и в других проектах.

| Компонент    | Описание |
|-------------|----------|
| **BaseButton** | Кнопка с вариантами `primary`, `danger`, `default`. Слот для содержимого. |
| **BaseInput**  | Текстовое поле с `v-model`, placeholder, disabled. |
| **EmptyState** | Заглушка для пустого списка/раздела. Проп `message` или слот. |

Импорт: `import { BaseButton, BaseInput, EmptyState } from '@/components/base'`

---

## Компоненты фичи Todo

Переиспользуются внутри фичи «список задач».

| Компонент  | Описание |
|-----------|----------|
| **TodoItem**  | Один элемент задачи (чекбокс, текст, кнопка удаления). События `toggle`, `remove`. |
| **TodoList**  | Список задач. Проп `items`, события `toggle`, `remove`. |
| **TodoInput** | Поле ввода + кнопка «Добавить». `v-model` + событие `add`. |

Импорт: `import { TodoItem, TodoList, TodoInput, type Todo } from '@/components/todo'`
