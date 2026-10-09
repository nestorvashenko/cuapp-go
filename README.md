# Шаблон приложения ColdOS — Go

Заготовка приложения ColdOS на Go.

> ColdOS исполняет JavaScript. Go-код не запускается как есть:
> `cldcli build` конвертирует поддерживаемое подмножество в JS
> (парсер `prgo.js`).

## Создание проекта

```bash
cldcli init myapp --lang go
```

## Поддерживаемое подмножество

| Возможность | Пример |
|---|---|
| Точка входа | `func user_run_application_<id>() { }` |
| Переменные | `x := "строка"`, `var y = 1` |
| Шаблоны | `fmt.Sprintf("текст %s", x)` |
| Словари | `map[string]interface{}{"k": v}` → `{ k: v }` |
| Списки | `[]string{"a", "b"}` → `["a", "b"]` |
| Логика | `if cond { }`, `else { }` |
| Возврат | `return`, `return value` |
| Вызовы ColdOS | `Window_add(...)`, `popup(...)` |

**Не поддерживается:** goroutine, `select`, `defer`, интерфейсы,
структуры, каналы, slices, generics, циклы `for`/`range`,
многозначные присваивания (`x, err := ...`).

## Структура

```
myapp/
├── src/
│   ├── main.go          # код приложения
│   └── index.css        # стили
├── assets/              # иконки
├── package.json
└── README.md
```

## Сборка

```bash
cldcli build
```