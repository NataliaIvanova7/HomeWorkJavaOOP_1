__В исходном коде ДЗ обнаружены нарушения принципов SOLID:__
1. В классе User были прописаны 2 разных метода - нарушение принципа единой ответственности (SRP).
2. Описание поведения сущности User путем задания методов в самом классе User - 
это нарушение принципа открытости-закрытости (OCP).

Решение: вынести каждый метод, описывающий поведение, в отдельный интерфейс
и добавить имплементации этих интерфейсов в класс User.

3. Внутри метода save в классе User происходило создание экземпляра класса Persister 
и вызов метода save класса Persister - нарушение принципа инверсии зависимостей (DIP).

Решение: класс Persister преобразовать в интерфейс, отвечающий за сохранение 
и содержащий метод save. Добавить имплементацию этого интерфейса классу User и 
реализацию метода save.
   

