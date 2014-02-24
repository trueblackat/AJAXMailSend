# AJAXMailSend
Отправка писем с помощью JQuery и PHP

### Подключение:

```javascript
    <script src="http://code.jquery.com/jquery-1.10.2.min.js"></script>
    <script src="js/mail_send.js"></script>
```

### Простое использование (обязательные параметры):

```javascript
    $('#form').ajaxMailSend({mail_to: "your@mail.com"});
```

### Дополнительные параметры:

```javascript
    $('#form').ajaxMailSend({
      mail_to : 'gafurovamir@gmail.com',
      show_message_block : true,  // показывать блок сообщений?
      ok_msg : 'Сообщение успешно отправлено!',
      req_err_msg : 'Вы не заполнили обязательные поля',
      email_err_msg : 'Укажите email для отправки данной формы',
      send_button : '.send',
      email_title : 'LETTER HEADER'
    });
```

### Настройки формы:

`name="name"` - идентификатор поля 

`data-caption="Имя пользователя:"` -  значение для подписи названия поля в письме

Для кнопки отправки задать класс `.send_button` (стандартный класс) для привязки скрипта. Также можно использовать любой другой класс, но в дополнительных параметрах при подключении указать `send_button : '.class'` .

```html
    <form action="#" id="form">
        <input type="text" name="name" data-caption="Имя пользователя:" class="required" placeholder="введите ваше имя"/>
        <input type="text" name="phone" data-caption="Телефон пользователя:" placeholder="введите ваш телефон"/>
        <input type="submit" class="send" value="Отправить"/>
    </form>
```


## История версий:

* **0.9** - Добавлены data- атрибуты для указания названия поля в письме;
* **0.8.1** - Исправлены мелкие ошибки, вызывавшие неправильное определение состояния отправки;
* **0.8** - Добавлено автоматиеское определение количества полей ввода, отныне лезть в php не нужно;
* **0.7** - Исправлены некоторые ошибки, конкретизация вывода ошибок, возможность самому задавать текст ошибок;
