# AJAXMailSend
Отправка писем с помощью JQuery и PHP

### Подключение:

```html
    <script src="http://code.jquery.com/jquery-1.10.2.min.js"></script>
    <script src="js/jquery.ajax-mail-send.js"></script>
```

### Простое использование (обязательные параметры):

Обязательными параметрами являются заголовок письма и email получателя. Их можно задавать следющими способами:

1. в параметрах при вызове:
```javascript
    $('#form').ajaxMailSend({mail_to: "to@mail.com", email_title : "LETTER HEADER"});
```

2. в data-атрибутах самой формы:
```javascript
    $('#form').ajaxMailSend();
```

```html
    <form id="form2" data-mailto="gafurovamir@gmail.com" data-email_title="Test email title">
```

### Одинаковые параметры для нескольких форм:

```javascript
    $('#form1, #form2').ajaxMailSend({mail_to: "to@mail.com"});

    $('#form3').ajaxMailSend({mail_to: "mail@to.com, req_err_msg: 'Заполните все поля!'"});
```

### Дополнительные параметры:

```javascript
    $('#form').ajaxMailSend({
      mail_to: '', // адрес отправки
      show_message_block: true,  // показывать блок сообщений?
      ok_msg: 'Сообщение успешно отправлено!',  // сообщение об успешной отправке
      req_err_msg: 'Вы не заполнили обязательные поля',  // сообщение ошибки валидатора
      email_err_msg: 'Укажите email для отправки данной формы',
      send_button: 'input[type="submit"]',  // кнопка отправки, если не указано в опциях при вызове, то input[type="submit"]
      email_title: '' // заголовок письма
    });
```

### Настройки формы:

`name="name"` - идентификатор поля 

`data-caption="Имя пользователя:"` -  значение для подписи названия поля в письме

Если для кнопка отправки формы не является `input[type="submit"]`, то следует указать в опциях при подключении
`send_button: '.class'`, где `'.class'` - это идентификатор данной кнопки, будь то `<button>` или любой другой элемент.

Чтобы указать обязательное поле, добавьте `class="required"`.

```html
    <form action="#" id="form">
        <input type="text" name="name" data-caption="Имя пользователя:" class="required" placeholder="введите ваше имя"/>
        <input type="text" name="phone" data-caption="Телефон пользователя:" placeholder="введите ваш телефон"/>
        <input type="submit" class="send" value="Отправить"/>
    </form>
```


## История версий:

* **0.9.3** - Добавлены data-атрибуты для самой формы для более лёгкого подключения;
* **0.9.2** - Возможность указывать одинаковые параметры для нескольких форм, независимых друг от друга;
* **0.9.1** - Включены в обработку textarea и select;
* **0.9** - Добавлены data- атрибуты для указания названия поля в письме;
* **0.8.1** - Исправлены мелкие ошибки, вызывавшие неправильное определение состояния отправки;
* **0.8** - Добавлено автоматиеское определение количества полей ввода, отныне лезть в php не нужно;
* **0.7** - Исправлены некоторые ошибки, конкретизация вывода ошибок, возможность самому задавать текст ошибок;
