---
title: "`<output>`"
description: "Элемент для вывода результатов вычислений или действий пользователя."
authors:
  - webdb81
contributors:
  - tatianafokina
keywords:
  - вывод результата
  - поле вывода
  - live regions
  - интерактивная область
  - живая область
related:
  - a11y/role-status
  - html/form
  - js/element-innertext
tags:
  - doka
---

## Кратко

Тег `<output>` позволяет выводить результаты вычислений или действий пользователя. Относится к элементам семантической вёрстки.

У тега есть встроенная роль [`status`](/a11y/role-status/). Благодаря ей [скринридеры](/a11y/screenreaders/) и другие вспомогательные технологии автоматически зачитывают содержимое тега, когда оно обновляется. Это делает часть страницы интерактивной или «живой» областью.

## Пример

```html
<form>
  <label for="people-num">
    Для скольких людей приготовить яичницу:
  </label>
  <input
    type="number"
    id="people-num"
    name="people"
    oninput="eggs.value = (parseInt(people.value) * 2)"
  >
  <p>Необходимое количество яиц:</p>
  <output role="status" name="eggs" for="people-num"></output>
</form>
```

## Как понять

Элемент `<output>` используется в тех случаях, когда пользователю надо показать результат работы программы в реальном времени, например:

- информация, которую пользователь вводит или изменяет в форме;
- вывод расчётов по данным, которые указал пользователь (калькулятор, гороскоп и тому подобное);
- всплывающие уведомления — тосты.

## Как пишется

- [`for`](/html/for/) — значением может быть один или несколько ID, разделённые пробелом. Указывает на связь перечисленных элементов ввода (например, [`<input>`](/html/input/)) с элементом `<output>`.
- `form` — указывается ID формы в этом же документе, с которой связывается поле вывода.
- `name` — имя поля вывода. Используется для подписи результата при отправке формы.

Чтобы тег работал во всех браузерах и со всеми скринридерами корректно, рекомендуют явно задавать ему `role="status"`.

`<output>` — парный тег. Допустимо вставлять пустой тег в разметку и _класть_ выводимое значение внутрь него при помощи JavaScript.

К тегу `<output>` также применяются все [глобальные атрибуты](/html/global-attrs/).

`<output>` можно связать с рейтингом, чтобы увидеть числовой результат.

<iframe title="Пример использования в форме с рейтингом" src="demos/form-rating/" height="200"></iframe>

Также тег можно использовать для вывода всплывающих уведомлений.

<iframe title="Пример всплывающего уведомления" src="demos/toast-notification/" height="350"></iframe>
