# Введение в списки Python

1. [] - создание списка. Каждое значение отделяется запятой и заключено в квадратные скобки ([]).

Пример:
> planets = ["Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune"] 

У каждого значения есть соответсвующий индекс который начинается с нуля 
Пример:

> print(planets[0])
> print(planets[1])
> print(planets[2])

Результатом выведет нам первый елемент списка под индексом 0 "Mercury"   
Вторым элементом списка с индексом 1 является Venus  
Третий же элемент по списку Earth(Земля)

` все индексы начинаются с 0, [1] — это второй элемент, [2] — третий и т. д. `

Можно также изменять значения в списке с помощью индекса.  

>	planets = ["Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune"]
	planets[3] = "Red Planet"
	print("Mars is also known as", planets[3])

Выходные данные: Mars is also known as Red Planet
2. Функция `len()**` - позволяет получить длину списка  
Создаем новую переменную `number_of_planets`. Код присваивает этой переменной число элементов в списке `planets (8)`
Пример:
> planets = ["Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune"]
	number_of_planets = len(planets)
	print("There are", number_of_planets, "planets in the solar system.")
	
Выходные данные: There are 8 planets in the solar system

3. `.append(value)` - вы можете добавлять или удалять элементы после создания списка. Чтобы добавить элемент в список, используйте метод  
Пример:
> planets = ["Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune"]
 `planets.append("Pluto")`
 number_of_planets = len(planets)
 print("There are actually", number_of_planets, "planets in the solar system.")
 
Выходные данные: There are actually 9 planets in the solar system.  

4. Метод `.pop()` - Вы можете удалить последний элемент в списке  
Пример:  
> planets = ["Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune", "Pluto"]
  planets.pop()  # Goodbye, Pluto
  number_of_planets = len(planets)
  print("No, there are definitely", number_of_planets, "planets in the solar system.")  
  
+ Индексы начинаются с нуля и возрастают. `Отрицательные индексы` начинаются с конца списка и работают в обратном направлении.
	`индекс -1 возвращает последний элемент в списке. Индекс -2 возвращает второе значение с конца.`
	
5. Метод списка `.index`

> planets = ["Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune"]
  jupiter_index = planets.index("Jupiter")
  print("Jupiter is the", jupiter_index + 1, "planet from the sun")  

Выходные данные: Jupiter is the 5 planet from the sun  
>[!Примечание]  
	Поскольку индексация начинается с 0, необходимо добавить 1, чтобы отобразить правильный номер.
	
6. Функция `max()` возвращает наибольшее число, а `min()` — наименьшее. 
`min(gravity_on_planets)` возвращает наименьшее число из списка gravity_on_planets, то есть 0,377 (Марс).  

>
	gravity_on_planets = [0.378, 0.907, 1, 0.377, 2.36, 0.916, 0.889, 1.12]
	bus_weight = 12650 # in Newtons, on Earth

	print("On Earth, a double-decker bus weighs", bus_weight, "N")
	print("The lightest a bus would be in the solar system is", bus_weight * min(gravity_on_planets), "N")
	print("The heaviest a bus would be in the solar system is", bus_weight * max(gravity_on_planets), "N")

## Срез списка

7. Часть списка можно извлечь с помощью среза. Срез использует квадратные скобки, но вместо одного элемента указывает начальный и конечный индексы.  
При использовании среза создается новый список, который начинается с начального индекса и заканчивается до конечного (не включая его).  
>
	planets = ["Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune"]
	planets_before_earth = planets[0:2]
	print(planets_before_earth)
Выходные данные: ['Mercury', 'Venus']

`Обратите внимание, что Земля не включена в список. Это связано с тем, что индекс заканчивается перед конечным индексом.`
Чтобы получить все планеты после Земли, выберите срез с 3 до 8:
>
	planets_after_earth = planets[3:8]
	print(planets_after_earth) 
Выходные данные: ['Mars', 'Jupiter', 'Saturn', 'Uranus', 'Neptune']

>[!Примечание]  
Если не поместить в срез конечный индекс, Python предполагает, что вы хотите дойти до конца списка:

`[!Важно] Срез создает новый список. Текущий список не изменяется.`

#### `Чтобы объединить два списка, используйте другой оператор (+) с двумя списками, чтобы получить новый список.`

8. Метод `.sort()` - метод для сортировки списка.  
Python сортирует список строк в алфавитном порядке и список чисел в числовом порядке:
> 
	amalthea_group = ["Metis", "Adrastea", "Amalthea", "Thebe"]
	galilean_moons = ["Io", "Europa", "Ganymede", "Callisto"]
	
	regular_satellite_moons = amalthea_group + galilean_moons
	regular_satellite_moons.sort()
	print("The regular satellite moons of Jupiter are", regular_satellite_moons)
Выходные данные: The regular satellite moons of Jupiter are ['Adrastea', 'Amalthea', 'Callisto', 'Europa', 'Ganymede', 'Io', 'Metis', 'Thebe']  
+ `.sort(reverse=True)` - сортировка в обратном порядке  
`! При использовании sort текущий список изменяется.`