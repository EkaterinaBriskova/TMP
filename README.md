# TMP
# Практика 0
```
@startuml
left to right direction
skinparam packageStyle rect

actor эксперт
actor соискатель_грантов
actor держатель_фонда

rectangle информационная_система_технической_экспертизы {
  
  соискатель_грантов--(подача заявки)
  соискатель_грантов--(выгодная презентация)

  (подача заявки) .> (независимая экспертиза)

  эксперт--(рассмотрение заявок)
  эксперт--(независимая экспертиза)
  
  (независимая экспертиза).> (выдача гранта)

  держатель_фонда--(оценка результата экспертизы)
  держатель_фонда--(выдача гранта)

}
@enduml

```

![0](https://user-images.githubusercontent.com/90749103/228903594-21f3ed13-3d28-4063-9bfd-51d4dd4d576c.png)


# Практика 1
```
@startuml
left to right direction
title Система технической экспертизы
actor Эксперт
actor Соискатель_грантов
actor держатель_фонда
rectangle Система {
держатель_фонда -- (организация мероприятия)
(организация мероприятия) ..>(подача заявки):<<include>>
(организация мероприятия) ..> (независимая экспертиза):<<include>>
(организация мероприятия) ..> (оценка результатов экспертизы):<<include>>

Соискатель_грантов -- (подача заявки)
(подача заявки) ..> (Выдача гранта):<<include>>
(независимая экспертиза) ..> (Выдача гранта):<<include>>
(оценка результатов экспертизы) ..> (Выдача гранта):<<include>>
Эксперт -- (независимая экспертиза)
}
@enduml

```
![Alt text](диаграммы/2.png)


```
Диаграмма классов
@startuml
class Эксперт{
+Паспортные данные
+ФИО
+Должность
Проверка()

}

class Соискатель_грантов{
+Паспортные данные
+ФИО соискателя
+Номер гранта
Регистрация Гранта()
}

class Грант{
+Номер гранта
+ФИО Представителя гранта
+Презентация Гранта
}

class Держатель_фонда{
+ФИО
+Должность
Оценка результата экспертизы()
Выдача гранта()
}

class СтатусГранта{
+Номер гранта
+Статус Гранта
+Отчет об экспертизе
}

class Выполнено{
+Грант проверен
}

Эксперт --> Грант:Проверяет
Соискатель_грантов --> Грант:Регистрация гранта
Держатель_фонда --> Грант:Выдает
Эксперт --> СтатусГранта:Изменяет статус
Держатель_фонда --> СтатусГранта:Оценивает результат экспертизы
СтатусГранта --> Выполнено
Грант --> Выполнено
Выполнено --> ВыдачаГранта

```
![2](https://user-images.githubusercontent.com/90749103/228903511-2f07ff60-7900-4260-9e43-feb364c0cf87.png)

