# FUMO2site.github.io
<!doctype html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
</head>
<body>

    <div class="d-flex flex-column flex-md-row align-items-center p-3 px-md-4 mb-3 bg-body border-bottom shadow-sm">
      <p class="h5 my-0 me-md-auto fw-normal">Тестирование ФУМО. Тема - инструментальные стали.</p>
      <nav class="my-2 my-md-0 me-md-3">
        <a class="p-2 text-dark" href="#">Тесты</a>
        <a class="p-2 text-dark" href="#">Результаты</a>
      </nav>
      <a class="btn btn-outline-primary" href="#">Вход для админа</a>
    </div>

    <form method="post">
        {%csrf_token%}
        <h1>Форма ввода вопроса</h1>
        <!-- В форме должен быть action, вызывающий отправку запроса на бэкенд -->



        <p><b>
        {% block v1 %}
        {{vopr.v1}}
        {% endblock %}
        </b></p>
        <p><input name="choice" type="radio" value="1"
        />{% block o1 %}
        {{vopr.v2}}
        {% endblock %}</p>
        <p><input name="choice" type="radio" value="2" />{% block o2 %}
        {{vopr.v3}}
        {% endblock %}</p>
        <p><input name="choice" type="radio" value="3" onclick=views.about2 />{% block o3 %}
        {{vopr.v4}}
        {% endblock %}</p>
        <p><input name="choice" type="radio" value="4" />{% block o4 %}
        {{vopr.v5}}
        {% endblock %}</p>
        <p><button type="submit" value="Дать ответ" /></p>


              <form action="main/contact_form.html" target="main/contact_form.html">
                <button>Форма контактов</button>
              </form>
       <!-- При нажатии на "Дать ответ" должен отправляться на бэкенд запрос, содержащий номер вопроса и номер ответа,
        бэкенд проверяет верность ответа по БД, и возвращает ответ с информацией о том, был ответ пользователя на
        тест верен или нет. Фронтенд получает ответ и отображает информацию из него -->
    </form>

</body>
</html>
