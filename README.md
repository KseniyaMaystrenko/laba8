# laba8
## Условие

![image](https://github.com/KseniyaMaystrenko/laba8/assets/152999073/d74c27c0-5bcd-4f5a-acec-f88c03225679)

## Объяснение программы

Эта программа на Python реализует игру "Крестики-нолики". Она создает графический интерфейс с кнопками 3x3, представляющими игровое поле. Два игрока по очереди ходят, нажимая на кнопки, показывая либо "X", либо "O" в соответствующей ячейке.

Программа отслеживает состояние игры и проверяет, выиграл ли кто-нибудь или нет. Она также проверяет наличие ничьей, когда все ячейки заполнены. Если один из игроков побеждает или возникает ничья, программа отображает соответствующее диалоговое окно и сбрасывает игру.

Для обработки исключений программа определяет класс исключения `InvalidMoveError`, который используется, когда игрок пытается сделать ход в уже занятую ячейку. Программа ловит это исключение и отображает сообщение об ошибке.

## Ответы

![image](https://github.com/KseniyaMaystrenko/laba8/assets/152999073/92c4faf6-d024-43c4-85e7-06fc9a4eb240)
![image](https://github.com/KseniyaMaystrenko/laba8/assets/152999073/bb43ca54-587e-464c-b439-0dfb4d270d99)
![image](https://github.com/KseniyaMaystrenko/laba8/assets/152999073/e67b600c-ad35-496b-85b8-d0f9721c42d0)

## Используемые источники

[Пишем игру крестики нолики на python](https://youtu.be/GElUzJ7-bcI?feature=shared)

# Условие для уровня medium

![image](https://github.com/KseniyaMaystrenko/laba8/assets/152999073/3696692f-4287-45b3-8b5f-a2d6403eef95)

## Объяснение программы

База данных в этой программе используется для хранения результатов игр в "Крестики-нолики".

1. **Подключение к базе данных**:
   - В методе create_database происходит подключение к базе данных SQLite с помощью sqlite3.connect("tictactoe_results.db"). Если файл базы данных не существует, он будет создан.
  
2. **Создание таблицы**:
   - После установления соединения, выполняется SQL-запрос для создания таблицы "results" с полями id, player1, player2 и winner. Этот запрос выполняется с использованием метода execute и сохраняет изменения в базе данных с помощью commit.

3. **Запись результата игры**:
   - При завершении каждой игры вызывается метод record_result, который записывает результат игры в таблицу базы данных. 
   - В этом методе используется объект cursor, который представляет указатель на текущую позицию в результирующем наборе запроса. 
   - Затем выполняется SQL-запрос INSERT INTO results (player1, player2, winner) VALUES (?, ?, ?), который добавляет новую запись с информацией о игроках и победителе (или о ничьей) в таблицу.
   - Параметры ("X", "O", winner) передают значения для заполнения вместо знаков вопроса в запросе.
   - После выполнения запроса данные сохраняются в базе данных с помощью commit.

Таким образом, каждый раз, когда игра заканчивается (победа одного из игроков или ничья), результат игры записывается в таблицу базы данных "results", что позволяет отслеживать и хранить историю результатов игр.

## Ответы

![image](https://github.com/KseniyaMaystrenko/laba8/assets/152999073/796e75fa-cd03-45d4-9264-ce71572a816a)

## Используемые источники
[База данных SQLite в Python. Создание БД, вставка в БД](https://youtu.be/K1C5JAo7cMU?si=9GjS0Fa5iRr5ob4F)

[SQLITE3 Создание таблицы, добавление данных, проверка и вывод. (неактуа](https://youtu.be/mRuylFh9wfY?si=ktQD6VPNJKi7LVm8)

