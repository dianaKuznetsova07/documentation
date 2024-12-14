@startuml

actor Покупатель

actor Администратор

rectangle Система {

usecase "Просматривать каталог книг" as UC1

usecase "Добавить книгу в корзину" as UC2

usecase "Оформить заказ" as UC3

usecase "Выбрать способ доставки" as UC4

usecase "Оплатить заказ" as UC5

usecase "Оформить возврат" as UC6

usecase "Добавить книгу в каталог" as UC7

usecase "Редактировать описание книги" as UC8

usecase "Удалить книгу" as UC9

usecase "Управлять категориями" as UC10

usecase "Авторизация" as UC11

}

Покупатель -- UC1

Покупатель -- UC2

Покупатель -- UC3

Покупатель -- UC4

Покупатель -- UC5

Покупатель -- UC6

UC3 ..> UC11 : include

UC4 ..> UC11 : include

UC5 ..> UC11 : include

Администратор -- UC7

Администратор -- UC8

Администратор -- UC9

Администратор -- UC10

Администратор -- UC11

@enduml