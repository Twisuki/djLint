---
description: djLint HTML Template linter включает более 30 правил! Найти определения можно здесь. Легко расширить, включив пользовательские правила!
title: Правила Линтера
keywords: облицовка шаблонов, форматер шаблонов, djLint, HTML, шаблоны, форматер, линтер, использование, правила
---

# Использование вкладышей

djLint включает в себя множество правил для проверки стиля и валидности ваших шаблонов. Используйте все преимущества линтера, настроив его на использование предустановленного профиля для выбранного вами языка шаблонов.

```bash
djlint /path/to/templates --lint

# with custom extensions
djlint /path/to/templates -e html.dj --profile=django

# or to file
djlint /path/to/this.html.j2  --profile=jinja
```

<div class="box notification is-info is-light">
    <span class="icon is-large"><i class="fas fa-2x fa-circle-arrow-right"></i></span><div class="my-auto ml-3 is-inline-block"><a href="/ru/docs/configuration/">Ознакомьтесь с руководством по настройке, чтобы узнать обо всех возможностях!</a></div>
</div>

## Включение или отключение правил

Большинство правил включены по умолчанию. Правила могут быть отключены в командной строке с помощью флага `--ignore`. Правила могут быть включены с помощью флага `--include`.

Например:

```bash
djlint . --lint --include=H017,H035 --ignore=H013,H015
```

Это также можно сделать через [{{ "configuration" | i18n }}]({{ "lang_code_url" | i18n }}/docs/configuration) файл.

## Правила

| Код  | Значение                                                                                                                  | По умолчанию |
| ---- | ------------------------------------------------------------------------------------------------------------------------- | ------------ |
| D004 | (Django) Статические урлы должны следовать шаблону {% raw %}`{% static path/to/file %}`{% endraw %}.                      | ✔️           |
| D018 | (Django) Внутренние ссылки должны использовать шаблон {% raw %}`{% url ... %}`{% endraw %}.                               | ✔️           |
| H005 | Html-тег должен иметь атрибут `lang`.                                                                                     | ✔️           |
| H006 | Тег `img` должен иметь атрибуты `height` и `width`.                                                                       | ✔️           |
| H007 | `<!DOCTYPE ... >` должен присутствовать перед тегом html.                                                                 | ✔️           |
| H008 | Атрибуты должны быть заключены в двойные кавычки.                                                                         | ✔️           |
| H009 | Имена тегов должны быть в нижнем регистре.                                                                                | ✔️           |
| H010 | Имена атрибутов должны быть в нижнем регистре.                                                                            | ✔️           |
| H011 | Значения атрибутов должны быть заключены в кавычки.                                                                       | ✔️           |
| H012 | Вокруг атрибута `=` не должно быть пробелов.                                                                              | ✔️           |
| H013 | Тег `img` должен иметь атрибуты alt.                                                                                      | ✔️           |
| H014 | Более 2 пустых строк.                                                                                                     | ✔️           |
| H015 | После тегов `h` следует перевод строки.                                                                                   | ✔️           |
| H016 | Отсутствие тега `title` в html.                                                                                           | ✔️           |
| H017 | Метки пустоты должны быть самозакрывающимися.                                                                             | -            |
| H019 | Замените `javascript:abc()` на событие `on_` и реальный url.                                                              | ✔️           |
| H020 | Найдена пустая пара тегов. Рассмотрите возможность удаления.                                                              | ✔️           |
| H021 | Следует избегать инлайн-стилей.                                                                                           | ✔️           |
| H022 | Используйте HTTPS для внешних ссылок.                                                                                     | ✔️           |
| H023 | Не используйте ссылки на сущности.                                                                                        | ✔️           |
| H024 | Опускайте тип в скриптах и стилях.                                                                                        | ✔️           |
| H025 | Тег кажется бесхозным.                                                                                                    | ✔️           |
| H026 | Пустые теги id и class могут быть удалены.                                                                                | ✔️           |
| H029 | Рассмотрите возможность использования строчных значений метода формы.                                                     | ✔️           |
| H030 | Рассмотрите возможность добавления мета-описания.                                                                         | ✔️           |
| H031 | Рассмотрите возможность добавления мета-ключевых слов.                                                                    | ✔️           |
| H033 | В действии формы обнаружен лишний пробел.                                                                                 | ✔️           |
| J004 | (Jinja) Статические урлы должны следовать шаблону {% raw %}`{{ url_for('static'...)}}`{% endraw %}.                       | ✔️           |
| J018 | (Jinja) Внутренние ссылки должны использовать шаблон {% raw %}`{% url ... %}`{% endraw %}.                                | ✔️           |
| T001 | Переменные должны быть заключены в пробел. Например: {% raw %}`{{ this }}`{% endraw %}                                    | ✔️           |
| T002 | В тегах следует использовать двойные кавычки. Ex {% raw %}`{% extends "this.html" %}`{% endraw %}                         | ✔️           |
| T003 | Конечный блок должен иметь имя. Например: {% raw %}`{% endblock body %}`{% endraw %}.                                     | ✔️           |
| T027 | В синтаксисе шаблона найдена незакрытая строка.                                                                           | ✔️           |
| T028 | Рассмотрите возможность использования тегов без пробелов внутри значений атрибутов. {% raw %}`{%- if/for -%}`{% endraw %} | ✔️           |
| T032 | В тегах шаблона обнаружены лишние пробелы.                                                                                | ✔️           |
| T034 | Вы намеревались использовать {% raw %}{% ... %} вместо {% ... }%?  {% endraw %}                                           | ✔️           |
| H035 | Meta должны быть самозакрывающимися.                                                                                      | -            |
| H036 | Избегайте использования тегов `br`.                                                                                       | -            |
| H037 | Найдено дублирование атрибута.                                                                                            | ✔️           |

### Кодовые шаблоны

Первая буква кода соответствует схеме:

::: content

- D: применяется специально для Django
- H: применяется к html
- J: применяется специально для Jinja
- M: применяется специально для Handlebars
- N: применяется специально для Nunjucks
- T: применяется в целом к шаблонам
  :::

### Добавление правил

Мы приветствуем запросы с новыми правилами!

Хорошее правило состоит из

::: content

- Name
- Code
- Message - Сообщение для отображения при обнаружении ошибки.
- Flags - Флаги регекса. По умолчанию используется re.DOTALL. например: re.I|re.M
- Patterns - regex-выражения, которые найдут ошибку.
- Exclude - Необязательный список профилей, из которых нужно исключить правило.
  :::

Пожалуйста, включите тест для проверки правила.

## Пользовательские правила

Создайте файл `.djlint_rules.yaml` рядом с вашим `pyproject.toml`. Правила могут быть добавлены в этот файл, и djLint подхватит их.

Хорошее правило выглядит следующим образом:

```yaml
- rule:
    name: T001
    message: Найти трихотилломанию
    flags: re.DOTALL|re.I
    patterns:
      - трихотилломанию
```
