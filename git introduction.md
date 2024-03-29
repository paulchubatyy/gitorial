Git introduction
================

Зміст:

* Інструменти
* Коміт
* Репозиторії
* Бранчування
* Оновлення
* Пуш
* Висновки

Інструменти
-----------

Зараз ми розглядатимемо консольний гіт клієнт і всі приклади будуть виконуватись в консолі. Хоча також існують графічні інструменти, зокрема SmartGit, які ви теж можете використовувати. Окрім цього, гіт добре інтегрується в наступні IDE: PhpStorm, Eclipse, Netbeans 7.0.1. Ви також можете використовувати ці IDE.

Коміт
-----

Гіт не комітить все підряд на відміну від СВН. Потрібно руками вказувати, що саме ми зібрались комітити. Для цього використовується наступна команда:

    git add <file/path>

Вказавши файли, які ви хочете комітити Гіт поставить їх в стейджинг зону. Стейджинг зона — це ті зміни, які будуть добавлені в наступний коміт. Після того, як ви добавили усі потрібні файли в стейджинг зону, прийшов час їх комітити. Це робиться наступною командою:

    git commit

Цей процес можна спростити. Для того, щоб закомітити всі зміни, як це робиться в СВН, можна виконати команду

    git commit -a

Власне на цьому етапі Гіт автоматично покладе усі зміни в стейджинг зону, а потім закомітить.

Репозиторії
-----------

Гіт — розприділена система контролю версій, тому кожна робоча копія являється власне репозиторієм. Репозиторії можуть обмінюватись між собою комітами, бранчами і тегами. Перед тим, як відправляти чи отримувати коміти з репозиторію, потрібно цей репозиторій вказати Гіту, щоб він про нього щось знав. Список віддалених репозиторіїв можна редагувати наступною командою:

    git remote <команда> # Де <команда> одна з наступних: show, add, rm

Відповідно щоб додати віддалений репозиторій потрібно виконати наступну команду:

    git remote add <локальна назва репозиторію> <url віддаленого репозиторію>

Бранчування
-----------

Однією з основних відмінностей Гіт від СВН є те, що механізм бранчів в Гіті є дуже дешевим. Всі бранчі (вітки) є локальними. Для створення бранча потрібно виконати наступну команду:

    git branch <назва нового бранча>

Створивши новий бранч непогано б було на нього переключитись опісля:

    git checkout <назва бранча>

Зауважте, цей процес відбуватиметься набагато швидше чим аналогічний в СВН через те, що всі бранчі є локальними. Також корисним буде створення локальних бранчів з їхнім мепінгом на бранчі в віддаленому репозиторії. Розглянемо це на прикладі: в віддаленому репозиторії origin є бранчі *master* і *develop*. В локальному репозиторії є бранч *master*. Нам потрібно створити локальний бранч *develop* і вказати Гіту, що він є відповідником бранча *develop* у віддаленому репозиторії. Для цього виконаємо наступні команди:

    git branch develop --track origin/develop

Оновлення
---------

Оновленні в Гіт відбувається з віддаленого репозиторію. Для того, щоб оновити локальний репозиторій з віддаленого, потрібно виконати наступну команду:

    git pull <локальна назва репозиторію> <назва віддаленого репозиторію>

Після чого всі коміти з віддаленого репозиторію будуть перенесені в локальний репозиторій. Якщо ми вказали, що локальний бранч є відповідником віддаленого, то команда матиме наступний вигляд.

    git checkout develop # Переключились на локальний бранч develop
    git pull # так як гіт знає про віддалений бранч, то відповідно витягне усі зміни з origin/develop в локальний бранч develop

Пуш або ж відправлення змін у віддалений репозиторій
----------------------------------------------------

Для того щоб відправити локальні зміни в віддалений репозиторій потрібно виконати наступну команду:

    git push <локальна назва віддаленого репозиторію> <назва віддаленого бранча>

Якщо ми вказали, що локальний бранч є відповідником віддаленого бранча, тоді можна вказувати просто

    git push

Висновки
--------

На лабораторній роботи ви отримали базові, але водночас достатні, знання для користування гітом у ваших повсякденних потребах.