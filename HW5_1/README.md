## Корректировки, внесенные в проект в ходе выполнения дз №5:
1. перенесла  package mapper в слой util
2. удалила избыточный слой dao, его содержимое перенесла в repository и поместила его в слой model
3. удалила из интерфейса GBRepository метод findById, т.к. для чтения, перезаписи и удаления
   используется метод readUser класса UserController, вызывающий внтури себя метод findAll интерфейса
   GBRepository.
4. изменила формат записи в файл - вместо записи через запятую, запись через пробел (класс UserMapper).
   Соответственно, в методе toOutput заменен разделитель при вызове split для создания из строки массива значений.
5. добавила метод delete в интерфейс GBRepository, его реализацию в классе UserRepository и обращение
   к нему в методе deleteUser класса UserController. Метод deleteUser, в свою очередь, вызывается
   в классе UserView в кейсе описания вызова команды DELETE в методе run
## Корректировки, внесенные в проект в ходе выполнения дз №7:
Использовала дизайн паттерн Builder для упрощения конструирования сущности User, 
имеющей несколько полей. В общем случае число полей может быть значительно большим, 
и часть из них в коде программы может задаваться опционально, поэтому использование данного паттерна
посчитала оправданным.

Изначально класс User имел 2 конструктора, принимающих 4 или 3 параметра.
Использование внутреннего класса UserBuilder дало возможность создать один универсальный 
конструктор, позволяющий задавать для объекта значения лишь тех полей, которые необходимы 
в каждом конкретном случае.

