# Набор памяток в Python строки

## Инструкции для применения в строках 

 >1. Метод **.split(' ')**, который включает в себя символ новой строки, разбивает строковые значения на отдельные строки. Разделит строку по каждому пробелу. При этом будет создан список всех слов или цифр, отделенных пробелом.
	
	temperatures = "Daylight: 260 F Nighttime: -280 F"
	temperatures_list = temperatures.split()
	print(temperatures_list)

	выходные данные:['Daylight:', '260', 'F', 'Nighttime:', '-280', 'F'] 

 > Можно использовать (\n) символ новой строки для разбиения строкового значения в конце каждой строки, создавая отдельные строки.


	
 >2. Метод **.title()** , возвращает первую букву каждого слова строки в верхний регистр. Такое же поведение и использование происходит в переменной.
 	
	print("temperatures and facts about the moon".title())
результат: Temperatures And Facts About The Moon

	heading = "temperatures and facts about the moon"
	heading_upper = heading.title()
	print(heading_upper)
результат: Temperatures And Facts About The Moon

>3. Поиску позиции определенного слова в строке заключается в использовании метода   **.find()**

	temperatures = """Saturn has a daytime temperature of -170 degrees Celsius, while Mars has -28 Celsius."""
	print(temperatures.find("Moon"))

Выходные данные: -1 {результат отрицательный так как в данной строке нет искомого слова}

	temperatures = """Saturn has a daytime temperature of -170 degrees Celsius, while Mars has -28 Celsius."""
	print(temperatures.find("Mars"))

Выходные данные: 64 {64 — это позиция, в которой в строке отображается "Mars"}


>4. Другой способ поиска содержимого заключается в использовании метода **.count()**, который возвращает общее число вхождений определенного слова в строке т.е посчитывает сколько раз искомое слово или символ встречается в строке.

	temperatures = """Saturn has a daytime temperature of -170 degrees Celsius, while Mars has -28 Celsius."""
	print(temperatures.count("Mars"))
	print(temperatures.count("Moon"))

Результат будет выглядеть как 1 и 0 

>5. Строки в Python чувствительны к регистру, что означает, что Луна и луна считаются разными словами. Чтобы выполнить сравнение без учета регистра, можно преобразовать строку в строчные буквы с помощью метода **.lower()**

	print("The Moon And The Earth".lower())
Выходные данные: the moon and the earth
>6. Метод **.upper()**, который делает противоположное, преобразуя каждый символ в верхний регистр
	
	print("The Moon And The Earth".upper())
Выходные данные: THE MOON AND THE EARTH

>7. Mетод **.isnumeric()**, **.isdecimal()** может проверять наличие строк, выглядящих как десятичные числа

	mars_temperature = "The highest temperature on Mars is about 30 C"
	for item in mars_temperature.split():
    	if item.isnumeric():
        	print(item)
Выходные данные: 30

> [!Важно!]
	> Если необходимо проверить отрицательные числа в строке, метод **.isnumeric()** работать не будет.

> 8. Для отрицательных чисел дефис добавляется к числу в качестве префикса, что может быть обнаружено с помощью метода **.startswith()**
	
	print("-60".startswith('-'))
Выходные данные: True
> 9. Метод **.endswith()** помогает проверить последний символ строки

	if "30 C".endswith("C"):
	print("This temperature is in Celsius")
Выходные данные: This temperature is in Celsius

> 10. Метод .replace() можно использовать для поиска и замены вхождений символа или группы символов.

	print("Saturn has a daytime temperature of -170 degrees Celsius, while Mars has -28 Celsius.".replace("Celsius", "C"))
Выходные данные: Saturn has a daytime temperature of -170 degrees C, while Mars has -28 C.

> 11. После разделения текста и выполнения преобразований, возможно, потребуется снова объединить все части. Так же, как метод .split() может разделять символы, метод **.join()** может соединить их обратно.

	Методу .join() требуется итерируемое значение (например, список Python) в качестве аргумента, поэтому его использование отличается от других строковых методов

	moon_facts = ["The Moon is drifting away from the Earth.", "On average, the Moon is moving about 4cm every year."]
	print(' '.join(moon_facts))
Выходные данные: The Moon is drifting away from the Earth. On average, the Moon is moving about 4cm every year.

В этом примере ' '(пустая строка) используется для присоединения каждого элемента в списке.

> 12. Метод **.format()** использует фигурные скобки ({}) в качестве заполнителей в строке, а присваивание переменных для замены текста.
	
	mass_percentage = "1/6"
	print("On the Moon, you would weigh about {} of your weight on Earth.".format(mass_percentage))
Выходные данные: On the Moon, you would weigh about 1/6 of your weight on Earth.

> 13. Начиная с версии Python 3.6 можно использовать f-строки. Эти строки выглядят как шаблоны и используют имена переменных из кода. Использование f-строк в предыдущем примере будет выглядеть следующим образом:

	print(f"On the Moon, you would weigh about {mass_percentage} of your weight on Earth.")
Выходные данные: On the Moon, you would weigh about 1/6 of your weight on Earth.

Переменные размещаются в фигурных скобках, а строка должна использовать префикс f.

> 14. Если нужно представить значение 1/6 в виде процента с одним десятичным разрядом, можно использовать функцию **round()** напрямую:

	print(round(100/6, 1))
Выходные данные: 16.7

В f-строках не нужно присваивать значение переменной заранее:

	print(f"On the Moon, you would weigh about {round(100/6, 1)}% of your weight on Earth.")
Выходные данные: On the Moon, you would weigh about 16.7% of your weight on Earth.

Использование выражения не требует вызова функции. Любой из строковых методов также является допустимым. Например, строка может применить определенный регистр для создания заголовка:

	subject = "interesting facts about the moon"
	heading = f"{subject.title()}"
	print(heading)
Выходные данные: Interesting Facts About The Moon