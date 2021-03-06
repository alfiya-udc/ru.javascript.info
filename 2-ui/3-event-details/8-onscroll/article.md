# Прокрутка

События прокрутки позволяют реагировать на прокрутку страницы или элемента. Есть много хороших вещей, которые можно сделать при этом.

Например:
- Показать/скрыть дополнительные элементы управления или информацию, основываясь на том, в какой части документа находится пользователь.
- Загрузить больше данных, когда пользователь прокручивает страницу вниз до конца.

Вот небольшая функция для отображения текущей прокрутки:

```js autorun
window.addEventListener('scroll', function() {
  document.getElementById('showScroll').innerHTML = pageYOffset + 'px';
});
```

```online
В действии:

Текущая прокрутка = <b id="showScroll">прокрутите окно</b>
```

Событие `scroll` работает как на `window`, так и на прокручиваемых элементах.

## Предотвращение прокрутки

Как можно сделать что-то непрокручиваемым? Нельзя предотвратить прокрутку, используя `event.preventDefault()` в обработчике `onscroll`, потому что он срабатывает *после* того, как прокрутка уже произошла.

Но можно предотвратить прокрутку, используя `event.preventDefault()` на событии, которое вызывает прокрутку.

Например:
- На событии `wheel` -- прокрутка колеса мыши ("прокручивание" тачпада также его генерирует).
- На событии `keydown` для клавиш `key:pageUp` и `key:pageDown`.

Если поставить на них обработчики, в которых вызвать `event.preventDefault()`, то прокрутка не начнётся.

Иногда это может помочь, но более надёжный способ -- использовать CSS, чтобы сделать что-то непрокручиваемым, например, свойство `overflow`.

Вот несколько задач, которые вы можете решить или просмотреть, чтобы увидеть применение `onscroll`.