.. todo::

    * Добавить cogapp

Шаблоны
=======

.. seealso::

   * `<https://ru.wikipedia.org/wiki/Шаблонизатор>`_

**Шаблонизатор** (в web) — это программное обеспечение, позволяющее
использовать `html-шаблоны` для генерации конечных `html-страниц`.

Основная цель использования **шаблонизаторов** — это отделение `представления
данных` от `исполняемого кода`. Часто это необходимо для обеспечения
возможности параллельной работы `программиста` и `дизайнера-верстальщика`.
Такой подход значительно ускоряет время разработки и прототипирования
приложения, дизайнеру не нужно вникать в программирование, а программисту
беспокоиться об интерфейсе.

Использование **шаблонизаторов** улучшает читаемость кода и упрощает внесение
изменений во внешний вид, когда проект целиком выполняет один человек.

Свою популярность шаблоны обрели с приходом фреймворка :l:`Ruby On Rails` и
стали популярны не только в Вебе, современные десктопные приложения тоже идут
по пути отделения логики программы от интерфейса, например библиотека
:l:`Electron` позволяет создавать GUI приложения с интерфейсом, написанном на
`HTML` + `JavaScript` и логикой на :l:`NodeJS`, по сути встраивая движок
`Chromium` в ваш исполняемый файл.

Другим примером является фреймворк :l:`Qt`, в котором интерфейс может быть
написан на `Qml` + `JavaScript` и запускаться независимо от основного
приложения при помощи утилиты ``qmlscene``. Компания `Microsoft` также
продвигает эту идею в `.Net`, предоставляя технологию `WPF
<https://ru.wikipedia.org/wiki/Windows_Presentation_Foundation>`_. Как мы
видим, некоторые принципы, ранее встречающиеся преимущественно в Вебе,
перенимаются другими областями программирования. Тем самым с развитием
Интернет Веб-технологии будут все больше влиять на программирование в целом.

.. figure:: /_static/6.www.sync/web/template.*

Шаблоны имеют очень простое определение — в статические файлы вставляются куски
кода, а при прогоне таких файлов через специальный транслятор (препроцессор), код
заменяется результатом его выполнения. Например, при компиляции шаблоны в `C++`
заменяются определенными значениями:

.. code-block:: cpp

    template< typename T >
    T min( T a, T b )
    {
      return a < b ? a : b;
    }

Перед компиляцией этот шаблон может принять такой вид:

.. code-block:: cpp

    int min( int a, int b )
    {
      return a < b ? a : b;
    }

    long min( long a, long b )
    {
      return a < b ? a : b;
    }

Если `Ruby` развивался как полноценный, интерпретируемый язык общего
назначения, который потом обрел фреймворк :l:`Ruby On Rails` и наконец систему
шаблонов, то `PHP` изначально был языком шаблонов, т.е. препроцессором, через
который можно прогнать любой файл (например, `HTML` со вставками `PHP`) и получить
результат.

Простой пример на `PHP`:

.. literalinclude:: /../examples/wsgi/3.templates/php/index.php
   :language: html+php
   :linenos:

Результат выполнения программы:

.. code-block:: html
    :caption: php index.php

    <html>
      <head>
         <title>
            Тестируем PHP
         </title>
      </head>
      <body>

      <h1>Hello, world!</h1>
      <br />

      * red <br />
    * green <br />
    * blue <br />
    * yellow <br />

      </body>
    </html>

.. toctree::
   :maxdepth: 3

   jinja2.rst
   mako.rst
   bash.rst
