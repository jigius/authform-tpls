# authform-tpls
Материалы для верстки виджета авторизации.

### Задача
Требуется сверстать шаблон для виджета, который будет работать на двух страницах, с разными шаблонами - десктоп и мобайл.

### Общие требования
1. Файл стилей виджета `/assets/task.css`
2. Селекторы стилей для виджета __не должны__ включать элементов
выше контейнера виджета `div.auth-content`. Исключением является только один селектор - `body.mobile`
для определения контекста мобильного шаблона.
3. Селекторы стилей должны включать `.auth-content`.
4. Нельзя использовать в качестве селекторов стилей классы элементов, которые начинаются с `-` (примеры: `-phone-edit`, `-processing`).
5. Нельзя использовать в качестве селекторов стилей классы элементов, которые содержат строку `-c0c9` (примеры: `auth-c0c9`, `helpBlock-c0c9`).
6. Содержимое js-шаблонов находится между строками с комментариями `<!-- html's chunks vvv -->` `<!-- html's chunks ^^^ -->` и 
должно быть __ИДЕНТИЧНЫМ__ для обоих шаблонов страниц.
7. Использование SASS/SCSS приветствуется, но не является необходимым.

### Общая информация

Вывод виджета на странице выполняется с помощью js-кода, с использованием тривиального [js-шаблонизатора](https://github.com/cho45/micro-template.js). 

Шаблоны, размешены в теле страниц и содержаться в script-элементах с `type="text/html"` с определенными id.
В шаблонах используется три конструкции:
 - `<% ... %>` - некие вычисления значений, с помощью js, которые будут использованы в шаблоне дальше. 
 - `<%= ... %>` - вставка данных в вывод с экранированием.
 - `<%=raw ... %>` - вставка данных в вывод без экранирования. Используется для вставки значений, содержащие html-код.

На каждой странице расположен нумерованный список состояний по отображению виджета. К каждому из состояний будет определены
требования к дизайну (которые будут размещены отдельно).

Для вывода состояний пункты 1,2 используется шаблон `id='tpl-auth-email'`

Для вывода состояний пункты 3-7 используется шаблон `id='tpl-auth-phone'` `token is not defined`

Для вывода состояний пункты 8-12 используется шаблон `id='tpl-auth-phone'` `token is defined`

[Онлайн версия](http://carlo.creachoo.ru/tasks/authform-tpls/)

### Страница с шаблоном для десктопной версии

Файл `/dsktp.html`

### Страница с шаблоном для мобильной версии

Файл `/mble.html`
