# Проект по React.js «Канбан-доска»

**Для запуска проекта выполнить:** ```npm start```
<br />**Примечание:** как и описывал в чате поддержки, возникла небольшая ошибка, при переносе задачи из одного списка в другой, нужно два раза кликнуть по задаче, чтобы она переместилась в нужный список.

### Функциональные требования
Исходная Канбан-доска должна иметь 4 блока с задачами:
<br /> * Backlog (задачи, которые требуют уточнения перед тем, как брать их в работу);
<br /> * Ready (задачи, которые могут быть взяты в работу);
<br /> * In progress (задачи, которые уже в работе);
<br /> * Finished (законченные задачи).


### 1. Добавление новой задачи
Первоначально каждая задача всегда размещается в бэклоге — для анализа. При клике на кнопку *«+ Add card»* в карточке Backlog должно появляться поле ввода в конце списка, между последней задачей и кнопкой. При этом кнопка *«+ Add card»* должна меняться на *«Submit»*. 

Алгоритм добавления задачи:  
Нажали кнопку *«+ Add card»* → появилось поле для редактирования → ввели название → нажали кнопку *«Submit»* — задача появилась в бэклоге (при условии, что название введено).

### 2. Перемещение задач между списками
Задачи для списка *Ready* берутся из *Backlog*. При клике на *«+ Add card»* в карточке *Ready*, в конце списка появляется дропдаун с задачами из списка *Backlog*. После клика на задачу из дропдауна она должна появиться в списке *Ready* последней, при этом эта задача должна быть удалена из *Backlog*.
Если *Backlog* пустой (в списке нет задач), то кнопка *«+ Add card»* в списке *Ready* должна быть неактивна, то есть при клике на неё ничего не происходит. Неактивной кнопке нужно назначить атрибут ```disabled```. Активная и неактивная кнопки должны отличаться визуально: например, цветом и отсутствием ```cursor: pointer```.
Остальные списки (*In progress* и *Finished*) работают по тому же принципу. Задачи для списка In progress берутся из *Ready*, а задачи для списка *Finished* — из *In progress*.

### 3. Сохранение внесенных изменений
Любые изменения, внесенные в приложение (добавление новых задач, перемещение задач между списками, изменение описания задачи), должны сохраняться в *localStorage*.
При загрузке приложения должны отображаться задачи, записанные в *localStorage* (или пустые списки, если в localStorage ничего нет). Если внести изменения и обновить страницу, то изменения должны сохраниться.

### 4. Детальная страница задачи
Добавить возможность перехода на отдельную страницу какой-либо задачи в списке при клике на её заголовок. Страница с задачей должна иметь URL, отличный от того, который используется для главной страницы. URL должен содержать id задачи. Пример: ```localhost:3000/tasks/12345``` откроет страницу задачи с ```id 12345```.

На детальной странице задачи должны быть выведены название задачи и её описание. Если описания нет, вывести вместо него фразу ```"This task has no description"```. Поле с описанием должно быть редактируемым. При клике на крестик в правом верхнем углу осуществляется переход обратно на главную страницу.

### 5. Вывод количества задач в футер
В футере должно быть выведено количество активных и завершенных задач.
<br /> * **Active tasks** — отображает количество задач в списке *Backlog*.
<br /> * **Finished tasks** — отображает количество задач в списке *Finished*.

### 6. Выпадающее меню пользователя
Реализовать выпадающий список, который будет появляться при клике на блок в правом верхнем углу страницы — аватар пользователя со стрелкой. Стрелочка рядом с аватаром должна смотреть вверх, когда меню открыто, и вниз, когда меню закрыто. При клике на пункты меню ничего не происходит, но нужно добавить выделение пунктов при наведении курсора (например, поменять цвет текста или добавить подчеркивание).
