# Циклы  
Памятка по использованию циклов `while` и `for`  
Что можно:
+ Понимать, когда использовать циклы `while` и `for`.
+ Несколько раз запускать задачу с помощью циклов `while`.
+ Выполнять циклический перебор данных списка с помощью циклов `for`

Для поддержки повторения цикла неизвестное число раз можно использовать цикл `while`.  
Цикл `while` выполняет операцию, пока определенное условие истинно.

> [!Важно]  
> Самое важное, что следует помнить при создании циклов while, — нужно обеспечить изменение условия. Если условие всегда истинно, Python продолжит выполнение кода до аварийного завершения программы.
Цикл `while` состоит из трех важных частей:  
+ Ключевое слово `while`, за которым следует пробел.  
+ Условие, которое вы тестируете. Если условие имеет значение `true`, код в цикле `while` выполняется.  
+ Код, который требуется запустить для каждой итерации, отступ с вложенным пробелом.

> while `<condition>`:  
  >  code here

Данный пример показывает как можно водить данные пока пользователь не введет слово `done` в нижнем регистре.  
> user_input = ''  
> while user_input.lower() != 'done':  
> ___user_input = input('Enter a new value, or done when done')

`[!Примечание]  
В нашем примере мы использовали .lower() для преобразования входных данных в нижний регистр, что позволяет выполнять сравнение без учета регистра.`  
[!Важно]  
`В Python нет цикла do.`
