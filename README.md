# C# Basics

Основното, което е нужно е .Net и Visual Studio

# If - else и If - else if

Конструкция, която позволява различни видове проверки

Условието в нея може да бъде:

`<=` (по малко или равно)

`>=` (по голямо или равно)

`==` (равно на)

`!= ` (различно от)

`<` (по малко)

`>` (по голямо)



В едно if условие може да има безкройно много проверки, които се свързват с `&&` или `||`, което може да изглежда така:
```
int a = 5; int b = 10;
if ( a > b && a > 2 ) //което връща true ако а е по-голямо и от b и от 2
if ( a > b || a > 2 ) //което връша true ако а е или по-голямо от b или по-голямо от 2
```

if else конструкцията се използва когато искаме да изпълним нещо ако if условието върне false

```
int a = 10; int b = 11;
if ( a == b ) { Console.WriteLine("a е равно на b") }
else Console.WriteLine("а не е равно на b")

```

Ако искате повече проверки ако if върне false, може да използвате if else if конструкция

Този вид конструкция също може да има безкрайно много else if проверки
```
int a = 10; int b = 11;
if (a == b) { Console.WriteLine("a е равно на b") }
else if ( a > b ) { Console.WriteLine("a е по голямо от b") }
else Console.WriteLine("a е по малко от b")
```

# For цикъл

For цикълът е много полезен при изпълнение на голям брой команди, които са обединени от един и същи алгоритъм,
той има една променлива, която в повечето случаи пази броя на завъртанията

```
for (int i = 0; i < 10; i++) 
{
  Console.WriteLine(i);
}
//това ще изпечата числата от 0 до 9
```

# While цикъл 

Подобен на for цикъла, този вид цикъл може да изпълнява голям брой команди, разликата е че няма променлива, която да пази броя на завъртанята

В повечето случаи този цикъл се използва в задачи, къдет отрябва да се приема вход, докато не се получи определена команда, в този случай, там където се слага условието, може да се сложи bool променлива, която да е равна на true и при определено условие да се сменява на false, при което цикъла ще приключи.


Основната разлика е, че при while цикъла, ние сами трябва да гарантираме, че той има край, което става чрез някакъв вид промяна в променливата, която е в условието
```
//пример за обикновен while цикъл
int a = 10;
while (a != 0) 
{
  Console.WriteLine(a);
  a--;
}
```

# Foreach цикъл


# Масиви []


# Листове List<>


# Речници Dictionary<>


# Ламбда и LINQ
