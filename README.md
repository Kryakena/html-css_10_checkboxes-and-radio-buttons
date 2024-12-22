# 🌕 Радиокнопка, чекбокс 🌞

Источник: видео "Стилизация чекбоксов и радиокнопок на CSS HTML jQuery // Как это сделать? // Фрилансер по жизни" 
https://vkvideo.ru/video-125918837_456239138?sel=19460369

![2024-12-22_21-32-18](https://github.com/user-attachments/assets/87e03cf9-69c4-4756-bedd-6dbb2a2f1bc9)


https://github.com/user-attachments/assets/52a3860e-f4c6-488d-a8a0-3795f3bcab27


1. создаем проект в программе "WebStorm" для работы с JavaScript (скачать бесплатную версию 
https://www.jetbrains.com/webstorm/)
2. создаем файлы index.html, style.css, script.js в папке проекта
3. в файле index.html готовим шаблон 

```html
<!--сообщаем браузеру, как стоит обрабатывать эту страницу-->
<!DOCTYPE html>
<!--оболочка документа, указываем язык содержимого-->
<html lang="ru">
<!--заголовок страницы, контейнер для других важных данных (не отображается)-->
<head>
    <!--заголовок страницы в браузере-->
    <title></title>
    <!--подключаем CSS-->
    <link rel="stylesheet" href="style.css">
    <!--кодировка страницы-->
    <meta charset="utf-8">
    <!--адаптив-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
</head>
<!--отображаемое тело страницы-->
<body>
<!--оболочка для демонстрации-->
<div class="wrapper">
    <!--контент-->

</div>
<!--
<script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
<script src="script.js"></script>
-->
</body>
</html>
```

4. в файле index.html подключаем jquery в body и вводим название проекта в head

```html
<title>"Элементы форм"</title>

<script src="https://code.jquery.com/jquery-3.4.1.slim.min.js"></script>
```

5. в файле index.html создаем формочку form с классом block-form в body

```html
<form action="#" class="block-form">
```

6. в файле index.html в созданной формочке добавим несколько элементов c атрибутом чек (checked)

```html
    <form action="#" class="block-form">
    <div class="block-form_title">Стили элементов форм</div>
    <div class="block-form_input">
        <div class="checkbox">
            Выключатель №1
            <input type="checkbox" checked name="namecheckbox_1">
        </div>
    </div>
    <div class="block-form_input">
        <div class="checkbox">
            Выключатель №2
            <input type="checkbox" name="namecheckbox_2">
        </div>
    </div>
```

7. в файле index.html в созданной формочке создаем еще радиокнопке

```html
        <div class="block-form_input">
    <div class="radiobuttons">
        <div class="radiobuttons_item">
            Вариант №1
            <input type="radio" value="1" checked name="nameradio_1">
        </div>
        <div class="radiobuttons_item">
            Вариант №2
            <input type="radio" value="2" name="nameradio_1">
        </div>
        <div class="radiobuttons_item">
            Вариант №3
            <input type="radio" value="3" name="nameradio_1">
        </div>
    </div>
</div>
```

8. в файле index.html создаем кнопку для папки form в разделе body в подразделе form

```html
<button class="button" type="submit">Отправить форму</button>
```

![8](https://github.com/user-attachments/assets/d5573699-cf15-455c-936e-902ccfebb043)


9. в файл style.css вставляем шаблон

```css
/*обнуление, которое убирает padding, margin, border*/
*,*:before,*:after {
    padding: 0;
    margin: 0;
    border: 0;
    /*вычисляет ширину контента, чтобы padding не учитывался*/
    -moz-box-sizing: border-box;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
}
html,body{
    height: 100%;
}
/*Стили для демонстрации*/
body{
    background-color: #eee; /*задний фон*/
    font-family: Arial, "Helvetica Neue", Helvetica, sans-serif; /*красивый шрифт*/
}
.wrapper{
    width: 100%;
    min-height: 100%;
    height: 100%;
    overflow: hidden;
    padding: 20px 30px; /*добавляем отступы*/
}
```

10. в файл style.css вставляем наши классы из HTML файла

```css
.block-form {}
.block-form_title {}
.block-form_input {}

/*Основые стили*/
.checkbox {}
.radiobuttons {}
.radiobuttons_item {}
.button {}
```

11. в файл style.css корректируем общие стили 

```css
.block-form_title { /*стиль заголовка*/
    font-size: 40px; /*размер шрифта*/
    margin-bottom: 20px; /*отступ вниз*/
}
.block-form_input {
    margin-bottom: 15px; /*отступ вниз*/
}
```

12. в файл script.js вставляем шаблон 

```js
$(document).ready(function () {
    
});
```

![11](https://github.com/user-attachments/assets/7c6043b8-4415-46bf-9551-4fff0f778847)


13. в файл script.js, чтобы связать элементы класса div в css c циклом for в скрипте
Для начала с помощью input проверяем чекбоксы

```js
$(document).ready(function () {

    //CHECKBOX
    $.each($('.checkbox'), function (index, val) {
        if($(this).find('input').prop('checked')==true){
            $(this).addClass('active');
        }
    });
});
```

14. в файле script.js создаем шаблон проверки чекбокса

```js
    $(document).on('click', '.checkbox', function (event) {
    if($(this).hasClass('active')) {

    }else{

    }

    return false;
});
```

15. в файле script.js создаем проверку чекбокса: если у нашего div чекбокса уже есть класс active, 
то мы убираем активность с input и наоборот

```js
    $(document).on('click', '.checkbox', function (event) {
    if($(this).hasClass('active')) {
        $(this).find('input').prop('checked', false);
    }else{
        $(this).find('input').prop('checked', true);
    }
    $(this).toggleClass('active');

    return false;
});
```

16. в файле style.css скрываем оригинальный input в .checkbox input

```css
.checkbox input{
    display: none; /*скрываем оригинальный чекбокс*/
}
```

17. в файле style.css стилизуем общий стиль переключатель с анимацией

```css
.checkbox {
    font-size: 16px;
    line-height: 20px;
    padding: 0px 0px 0px 70px;
    position: relative;
    cursor: pointer;
    color: #b2b2b2;

    transition: all 0.3s ease 0s;
    -webkit-transition: all 0.3s ease 0s;
    -moz-transition: all 0.3s ease 0s;
    -ms-transition: all 0.3s ease 0s;
    -o-transition: all 0.3s ease 0s;
}
```

18. в файле style.css стилизуем стиль самого переключателя (подложка)

```css
.checkbox:before{
    content: '';
    width: 50px;
    height: 20px;
    border-radius: 20px;
    background-color: #bfc0c4;
    position: absolute;
    left: 0;
    top: 0;
    -webkit-box-shadow: 0 0 3px rgba(0, 0, 0, 0.3);
    box-shadow: 0 0 3px rgba(0, 0, 0, 0.3);
}
```

19. в файле style.css стилизуем бегунок

```css
.checkbox:after{
    content: '';
    position: absolute;
    width: 30px;
    height: 30px;
    left: 0;
    top: -5px;
    background-color: #bfc0c4;
    border-radius: 50%;
    -webkit-box-shadow: 0 0 3px rgba(0, 0, 0, 0.3);
    box-shadow: 0 0 3px rgba(0, 0, 0, 0.3);
}
```

20. в файле style.css заставим все это работать

```css
.checkbox.active{
    color: #000;
}

.checkbox.active:before{
    background-color: #4fbb65;
}

.checkbox.active:after{
    background-color: #4fbb65;
    left: 25px;
}
```

![20](https://github.com/user-attachments/assets/39a7d56d-13fc-4df5-8419-a60199ac8528)


21. в файле script.js в $(document).ready создаем логику на радиокнопки 

```js
    //RADIO
$.each($('.radiobuttons_item'), function (index, val) {
    if($(this).find('input').prop('checked')==true){
        $(this).addClass('active');
    }
});
$(document).on('click', '.radiobuttons_item', function (event) {

    return false;
});
```

22. в файле script.js в $(document).ready логика радиокнопки будет отличаться от чекбокса

```js
    //RADIO
$.each($('.radiobuttons_item'), function (index, val) {
    if($(this).find('input').prop('checked')==true){
        $(this).addClass('active');
    }
});
$(document).on('click', '.radiobuttons_item', function (event) {
    $(this).parents('.radiobuttons').find('.radiobuttons_item').removeClass('active');
    $(this).parents('.radiobuttons').find('.radiobuttons_item input').prop('checked', false);
    $(this).toggleClass('active');
    $(this).find('input').prop('checked', true);
    return false;
});
```

23. в файле style.css стилизуем наши радиокнопки

```css
.radiobuttons_item {
    position: relative;
    padding: 0px 0px 0px 45px;
    font-size: 16px;
    line-height: 30px;
    color: #b2b2b2;
    margin-bottom: 20px;

    cursor: pointer;

    transition: all 0.3s ease 0s;
    -webkit-transition: all 0.3s ease 0s;
    -moz-transition: all 0.3s ease 0s;
    -ms-transition: all 0.3s ease 0s;
    -o-transition: all 0.3s ease 0s;
}

.radiobuttons_item:before{
    content: '';
    width: 30px;
    height: 30px;
    position: absolute;
    left: 0;
    top: 0;
    background-color: #bfc0c4;
    border-radius: 50%;
    -webkit-box-shadow: 0 0 3px rgba(0, 0, 0, 0.3);
    box-shadow: 0 0 3px rgba(0, 0, 0, 0.3);
}

.radiobuttons_item:after{
    content: '';
    position: absolute;
    width: 20px;
    height: 20px;
    left: 5px;
    top: 5px;
    background-color: #4fbb65;
    border-radius: 50%;

    transition: all 0.3s ease 0s;
    -webkit-transition: all 0.3s ease 0s;
    -moz-transition: all 0.3s ease 0s;
    -ms-transition: all 0.3s ease 0s;
    -o-transition: all 0.3s ease 0s;

    transform: scale(0);
    -moz-transform: scale(0);
    -ms-transform: scale(0);
    -webkit-transform: scale(0);
    -o-transform: scale(0);
}

.radiobuttons_item input{
    display: none;
}
```

24. в файле style.css заставим наши радиокнопки работать

```css
.radiobuttons_item.active{
    color: #000;
}

.radiobuttons_item.active:after{
    transform: scale(1);
    -moz-transform: scale(1);
    -ms-transform: scale(1);
    -webkit-transform: scale(1);
    -o-transform: scale(1);
}
```

25. в файле style.css стилизуем кнопку "Отправить форму"

```css
.button {
    line-height: 60px;
    display: inline-block;
    cursor: pointer;
    text-transform: uppercase;
    letter-spacing: 8px;
    padding: 0px 30px;
    font-size: 18px;
    border-radius: 25px;
    background-color: #bfc0c4;

    position: relative;
    overflow: hidden;

    transition: all 0.3s ease 0s;
    -webkit-transition: all 0.3s ease 0s;
    -moz-transition: all 0.3s ease 0s;
    -ms-transition: all 0.3s ease 0s;
    -o-transition: all 0.3s ease 0s;
}
```

26. в файле style.css заставляем кнопку "Отправить форму" работать

```css
.button:before{
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    border-radius: 25px;
    left: 0;
    background-color: #4fbb65;

    transform: scale(0);
    -moz-transform: scale(0);
    -ms-transform: scale(0);
    -webkit-transform: scale(0);
    -o-transform: scale(0);
    
    transition: all 0.3s ease 0s;
    -webkit-transition: all 0.3s ease 0s;
    -moz-transition: all 0.3s ease 0s;
    -ms-transition: all 0.3s ease 0s;
    -o-transition: all 0.3s ease 0s;
}

.button:hover{

}
```

27. в файле index.html в form обернем текст кнопки "Отправить форму" в span, 
чтобы достать его наружу

```html
<button class="button" type="submit"><span>Отправить форму</span></button>
```

28. в файле style.css создаем span

```css
.button span{
    position: relative;
    z-index: 2;
}
```

29. в файле style.css стилизуем дальше кнопку "Отправить форму"

```css
.button:hover{
    color: #fff;
}
.button:hover:before{
    transform: scale(1);
    -moz-transform: scale(1);
    -ms-transform: scale(0);
    -webkit-transform: scale(1);
    -o-transform: scale(1);
}
```

# Итог

1. в файле style.css

```css
/*обнуление, которое убирает padding, margin, border*/
*,*:before,*:after {
    padding: 0;
    margin: 0;
    border: 0;
    /*вычисляет ширину контента, чтобы padding не учитывался*/
    -moz-box-sizing: border-box;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
}
html,body{
    height: 100%;
}
/*Стили для демонстрации*/
body{
    background-color: #eee; /*задний фон*/
    font-family: Arial, "Helvetica Neue", Helvetica, sans-serif; /*красивый шрифт*/
}
.wrapper{
    width: 100%;
    min-height: 100%;
    height: 100%;
    overflow: hidden;
    padding: 20px 30px; /*добавляем отступы*/
}
.block-form {}
.block-form_title { /*стиль заголовка*/
    font-size: 40px; /*размер шрифта*/
    margin-bottom: 20px; /*отступ вниз*/
}
.block-form_input {
    margin-bottom: 15px; /*отступ вниз*/
}

/*Основые стили*/
.checkbox {
    font-size: 16px;
    line-height: 20px;
    padding: 0px 0px 0px 70px;
    position: relative;
    cursor: pointer;
    color: #b2b2b2;

    transition: all 0.3s ease 0s;
    -webkit-transition: all 0.3s ease 0s;
    -moz-transition: all 0.3s ease 0s;
    -ms-transition: all 0.3s ease 0s;
    -o-transition: all 0.3s ease 0s;
}

.checkbox.active{
    color: #000;
}

.checkbox.active:before{
    background-color: #4fbb65;
}

.checkbox.active:after{
    background-color: #4fbb65;
    left: 25px;
}

.checkbox:before{
    content: '';
    width: 50px;
    height: 20px;
    border-radius: 20px;
    background-color: #bfc0c4;
    position: absolute;
    left: 0;
    top: 0;
    -webkit-box-shadow: 0 0 3px rgba(0, 0, 0, 0.3);
    box-shadow: 0 0 3px rgba(0, 0, 0, 0.3);
}

.checkbox:after{
    content: '';
    position: absolute;
    width: 30px;
    height: 30px;
    left: 0;
    top: -5px;
    background-color: #bfc0c4;
    border-radius: 50%;
    -webkit-box-shadow: 0 0 3px rgba(0, 0, 0, 0.3);
    box-shadow: 0 0 3px rgba(0, 0, 0, 0.3);
}

.checkbox input{
    display: none; /*скрываем оригинальный чекбокс*/
}


.radiobuttons {}
.radiobuttons_item {
    position: relative;
    padding: 0px 0px 0px 45px;
    font-size: 16px;
    line-height: 30px;
    color: #b2b2b2;
    margin-bottom: 20px;

    cursor: pointer;

    transition: all 0.3s ease 0s;
    -webkit-transition: all 0.3s ease 0s;
    -moz-transition: all 0.3s ease 0s;
    -ms-transition: all 0.3s ease 0s;
    -o-transition: all 0.3s ease 0s;
}

.radiobuttons_item.active{
    color: #000;
}

.radiobuttons_item.active:after{
    transform: scale(1);
    -moz-transform: scale(1);
    -ms-transform: scale(1);
    -webkit-transform: scale(1);
    -o-transform: scale(1);
}

.radiobuttons_item:before{
    content: '';
    width: 30px;
    height: 30px;
    position: absolute;
    left: 0;
    top: 0;
    background-color: #bfc0c4;
    border-radius: 50%;
    -webkit-box-shadow: 0 0 3px rgba(0, 0, 0, 0.3);
    box-shadow: 0 0 3px rgba(0, 0, 0, 0.3);
}

.radiobuttons_item:after{
    content: '';
    position: absolute;
    width: 20px;
    height: 20px;
    left: 5px;
    top: 5px;
    background-color: #4fbb65;
    border-radius: 50%;

    transition: all 0.3s ease 0s;
    -webkit-transition: all 0.3s ease 0s;
    -moz-transition: all 0.3s ease 0s;
    -ms-transition: all 0.3s ease 0s;
    -o-transition: all 0.3s ease 0s;

    transform: scale(0);
    -moz-transform: scale(0);
    -ms-transform: scale(0);
    -webkit-transform: scale(0);
    -o-transform: scale(0);
}

.radiobuttons_item input{
    display: none;
}

.button {
    line-height: 60px;
    display: inline-block;
    cursor: pointer;
    text-transform: uppercase;
    letter-spacing: 8px;
    padding: 0px 30px;
    font-size: 18px;
    border-radius: 25px;
    background-color: #bfc0c4;

    position: relative;
    overflow: hidden;

    transition: all 0.3s ease 0s;
    -webkit-transition: all 0.3s ease 0s;
    -moz-transition: all 0.3s ease 0s;
    -ms-transition: all 0.3s ease 0s;
    -o-transition: all 0.3s ease 0s;
}

.button span{
    position: relative;
    z-index: 2;
}
.button:before{
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    border-radius: 25px;
    left: 0;
    background-color: #4fbb65;

    transform: scale(0);
    -moz-transform: scale(0);
    -ms-transform: scale(0);
    -webkit-transform: scale(0);
    -o-transform: scale(0);

    transition: all 0.3s ease 0s;
    -webkit-transition: all 0.3s ease 0s;
    -moz-transition: all 0.3s ease 0s;
    -ms-transition: all 0.3s ease 0s;
    -o-transition: all 0.3s ease 0s;
}

.button:hover{
    color: #fff;
}
.button:hover:before{
    transform: scale(1);
    -moz-transform: scale(1);
    -ms-transform: scale(0);
    -webkit-transform: scale(1);
    -o-transform: scale(1);
}
```

![2024-12-22_21-30-08](https://github.com/user-attachments/assets/64c921e9-74e4-43fd-8801-f1da03fe641f)
![2024-12-22_21-30-27](https://github.com/user-attachments/assets/b3863ef0-4b8c-46ce-9816-84bab6cedf92)
![2024-12-22_21-30-43](https://github.com/user-attachments/assets/215d323e-5aff-4318-9073-995ac87d199d)
![2024-12-22_21-31-00](https://github.com/user-attachments/assets/b6274ad6-2a42-444b-8ca9-be0d7828f0f8)
![2024-12-22_21-31-15](https://github.com/user-attachments/assets/cb814226-3da5-4a5d-a8cf-820755679725)


2. в файле index.html

```html
<!--сообщаем браузеру, как стоит обрабатывать эту страницу-->
<!DOCTYPE html>
<!--оболочка документа, указываем язык содержимого-->
<html lang="ru">
<!--заголовок страницы, контейнер для других важных данных (не отображается)-->
<head>
    <!--заголовок страницы в браузере-->
    <title>"Элементы форм"</title>
    <!--подключаем CSS-->
    <link rel="stylesheet" href="style.css">
    <!--кодировка страницы-->
    <meta charset="utf-8">
    <!--адаптив-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
</head>
<!--отображаемое тело страницы-->
<body>
<!--оболочка для демонстрации-->
<div class="wrapper">
    <!--контент-->
    <form action="#" class="block-form">
        <div class="block-form_title">Стили элементов форм</div>
        <div class="block-form_input">
            <div class="checkbox">
                Выключатель №1
                <input type="checkbox" checked name="namecheckbox_1">
            </div>
        </div>
        <div class="block-form_input">
            <div class="checkbox">
                Выключатель №2
                <input type="checkbox" name="namecheckbox_2">
            </div>
        </div>
        <div class="block-form_input">
            <div class="radiobuttons">
                <div class="radiobuttons_item">
                    Вариант №1
                    <input type="radio" value="1" checked name="nameradio_1">
                    <!--checked - по умолчанию тут будет чек-->
                </div>
                <div class="radiobuttons_item">
                    Вариант №2
                    <input type="radio" value="2" name="nameradio_1">
                </div>
                <div class="radiobuttons_item">
                    Вариант №3
                    <input type="radio" value="3" name="nameradio_1">
                </div>
            </div>
        </div>
        <button class="button" type="submit"><span>Отправить форму</span></button>
    </form>
</div>
<!--подключаем jQuery-->
<script src="https://code.jquery.com/jquery-3.4.1.slim.min.js"></script>
<!--подключаем файл JS скриптов-->
<script src="script.js"></script>
</body>
</html>
```

![2024-12-22_21-31-32](https://github.com/user-attachments/assets/06a25827-1dc9-480a-a3f9-a5996a7c14d0)
![2024-12-22_21-31-58](https://github.com/user-attachments/assets/ddd74318-f362-4efb-950d-2e1f37144fa7)


3. в файле script.js

```js
$(document).ready(function () {

    //CHECKBOX
    $.each($('.checkbox'), function (index, val) {
        if($(this).find('input').prop('checked')==true){
            $(this).addClass('active');
        }
    });
    $(document).on('click', '.checkbox', function (event) {
        if($(this).hasClass('active')) {
            $(this).find('input').prop('checked', false); //проверка
        }else{
            $(this).find('input').prop('checked', true); //проверка
        }
        $(this).toggleClass('active'); //проверка

        return false;
    });

    //RADIO
    $.each($('.radiobuttons_item'), function (index, val) {
        if($(this).find('input').prop('checked')==true){
            $(this).addClass('active');
        }
    });
    $(document).on('click', '.radiobuttons_item', function (event) {
        $(this).parents('.radiobuttons').find('.radiobuttons_item').removeClass('active');
        $(this).parents('.radiobuttons').find('.radiobuttons_item input').prop('checked', false);
        $(this).toggleClass('active');
        $(this).find('input').prop('checked', true);
        return false;
    });
});
```

![2024-12-22_21-29-48](https://github.com/user-attachments/assets/00e39c0a-1c68-45fa-97b0-5ad71ecd9235)
