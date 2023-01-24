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

В повечето случаи този цикъл се използва в задачи, където трябва да се приема вход, докато не се получи определена команда, в този случай, там където се слага условието, може да се сложи bool променлива, която да е равна на true и при определено условие да се сменява на false, при което цикъла ще приключи.


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

```
//пример за while цикъл по начина, който обясних
bool check = true;
while (check)
{
  if (Console.ReadLine() == "Stop") check = false; 
}
```

# Методи

Методите са отделна част от код, която може да бъде извиквана на различни места в основния код. Всеки метод си има име и параметри, с които да бъде извикан.
```
public static void Main(string[] args)
{
  //тук се пише основния код, който се изпълнява винаги
  //долният метод може да се извика тук по този начин
  Add(10, 12);
  //това ще изпише на конзолата 22
}

//това е метод с името Add
//той има параметри a и b, които са цели числа
static void Add(int a, int b)
{
  //всичко което прави този метод е да изпечата на конзолата сбора на a и b
  Console.WriteLine(a + b);
}
```
Този примерен метод не връща никаква стойност, затова е от тип `void`.
Ако искаме да връща нещо, променяме типа void, на желания тип данни, които ще върнем.
Ако искаме да върнем цяло число, метода ще изглежда като `static int Add(int a, int b)`

Тогава кода ще изглежда така
```
public static void Main(string[] args)
{
  //така запазваме връщаната стойност в променлива
  int a = Add(10, 12);
  //можем и директно да го изпечатаме като
  Console.WriteLine(Add(10, 12));
}

static int Add(int a, int b)
{
  //връщаме сбора на двете чрез думата `return`
  return a + b;
}
```
Важно е когато един метод не е от тип void, той винаги трябва да връща нещо чрез return.
Този return може да бъде в if - else и подобни, но винаги трябва да го има!

Също може да има и методи без параметри. Броя на параметрите не е от значение!
Накратко за параметрите: Те са променливи от тип (може да е всякакъв и да са различни едно от друго), които могат да се използват само в границите на метода!
Когато се извиква метода, винаги се подава точния брой параметри и точните типове данни!

# Масиви []

Масивите са колекция от един и същ тип данни, с определена дължина (Length), която не може да се променя. Могат да се създадат празни и след това да се напълнят, или пък да се създадат със зададени стойности. Всеки елемент от масива си има определен индекс. Индексите започват от 0, демек първият елемент на масива има индекс 0. В повечето случаи, с масиви се оперира чрез for цикъл, както е показано в примера.

До елементи от масива се достъпва чрез името на масива и до него в [] се слага индекса (пример: arr[2] (може да се ползва и променлива както е в примера))
```
//създаване на празен масив от int с дължина 5 елемента
int[] arr = new int[5];

//създаване на попълнен масив от тип string с дължина от 5 елемента (не може да се напълни с по малко елементи) 
string[] arr = new string[5] { "a", "b", "c", "d", "e"};

//обикаляне на всеки елемент от масива
int[] arr = new int[3] {1, 2, 3};

for (int i = 0; i < arr.Length; i++)
{
  Console.WriteLine(arr[i]);
}

```

# Нужни са допълнителни библиотеки за следващите неща

# Листове List<> 
(за да се ползва най-отгоре на кода се пише `` using System.Collections.Generic; ``)

![image](https://user-images.githubusercontent.com/92583822/166870566-0c632f40-6137-4e5b-8f91-1eda1ba6cb93.png)

Листовете са много по функционални масиви. Листовете пак са колекция от един и същ вид данни, но имат променлива дължина. Може да се добавят и премахват елементи. Имат доста допълнителни команди, които може да си видят в примерите.

```
//декларация на лист от тип int (следващите команди са примери с този лист)
List<int> list = new List<int>();

//намиране на дължината на листа ( броя елементи в него )
list.Count;

//добавяне на елементи
list.Add(15);

//премахване на определен елемент (първият който срещне)
list.Remove(5);//премахва една петица

//премахване на елемент на определена позиция
list.RemoveAt(3)//премахва елемента на индекс 3

```
Обикалянето на листа се случва като при масива


# Речници Dictionary<>
(за да се ползва най-отгоре на кода се пише `` using System.Collections.Generic; `` както при листовете)

Речниците са колекция от данни, които могат да се достъпват чрез определен ключ, а не индекс. Не може да се повтаря един и същи ключ! При създаването им се определя типа на ключа и типа на елементите на които ще отговаря, пример за речник с тип на ключ int и стойност string -> `` Dictionary<int, string> dict = new Dictionary<int, string>(); ``. Той също няма ограничение на дължината, но при работата с речник се използват проверки за да се избегнат грешки! 

.ContainsKey() се използва за да се провери дали този ключ вече съществува (връща bool стойност)
```
//пример за проверка дали речника съдържа ключ 4
Dictionary<int, string> dict = new Dictionary<int, string>();
if (dict.ContainsKey(4)) {  }
```
За следващите операции е добре да се направи първо проверката дали съществува такъв ключ


За добавяне на нов ключ, задължително се подава и стойност, пример:
```
Dictionary<int, string> dict = new Dictionary<int, string>();
dict.Add(4, "Pesho");
```
Ако искаме да опрерираме със стойноста на която отговаря ключа, положението е подобно като при масивите
```
Dictionary<string, int> dict = new Dictionary<string, int>();
dict["Pesho"] = 20;
```


Ако изкаме да изпринтим речника използваме нов вид цикъл, който се използва основно за печатане
Цикъла е foreach, той не работи със стойност, а автоматично взима всяка една стойност от подадената му колекция и я дава в променлива, с която да оперираме
Foreach цикъла е най безопасен от страна на грешки, но в повечето случаи не е полезен за работа с данните, основно е за печатане!
Пример за foreach цикъл на речник
```
foreach (var pair in dict) //var е самият вид на променливата pair, когато работим с речник или нещо по сложно си е най добре да я оставим var
{

}
```
За да изпечатаме речника, foreach цикъла изглежда така:
```
foreach (var pair in dict)
{
    Console.WriteLine($"{pair.Key} -> {pair.Value}"); // би изпечатало примерно 5 -> Pesho 
}
```


# Ламбда и LINQ
(за да се ползва най-отгоре на кода се пише `` using System.Linq; `` )

![image](https://user-images.githubusercontent.com/92583822/166873306-3fb8bfd7-5cf6-4468-8c00-fce2f68091c7.png)

Тази библиотека не ни показва нов тип данни, тя ни помага за работата с колекции от данни. Има методи за сортиране, разделяне и тн.
Основните които се използват са:

```
string a = "Linq is super useful!";
string[] b = a.Split(' ').ToArray(); //.Split(' ') разделя сподадения стринг по интервали, а .ToArray() го обединява в масива b

//ако искаме да работим с числа
string a = "1, 2, 3, 4, 5, 6, 7, 8, 9";
int[] b = a.Split(", ").Select(int.Parse).ToArray();//в този случай разделяме стринга по ", ", и след това го парсваме чрез .Select(int.Parse)
//.Select() има много уптреби, защото чрез него може да променяме всеки елемент от колекцията

//ако искаме елементите да отговарят на условия
string a = "1, 2, 3, 4, 5, 6, 7, 8, 9";
int[] b = a.Split(", ").Select(int.Parse).Where(x => x % 2 == 0).ToArray();//тук вече използваме ламба(=>) при Where
//.Where() се използва за проверки на всеки един елемент от колекцията, ако отговаря на условието, той се добавя към масива
//използва се ламбда за да се покаже променливата, ако сме написали x =>, натам използваме х за да символизираме елемента от масива
//масива b в момента съдържа само четни числа
```
