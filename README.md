# Шпаргалка по C# - ConstructG.com (перевод на русский: mesheni)

**Версия:** 1.0.1

**Версия фреймворка:** .NET Core 3.1.9 или новее.

**Версия языка:** С# 8.0 или более поздняя версия.

## Оглавление

- [C# Шпаргалка](#)
  - [О шпаргалке](#about)
  - [Введение в С#](#Введение-в-С#)
    - [Что такое С#?](#what-is-c)
    - [Для чего используется C#?](#what-is-c-used-for)
  - [Ключевые слова С#](#c-keywords)
    - [Зарезервированные ключевые слова](#reserved-keywords)
    - [Контекстные ключевые слова](#contextual-keywords)
  - [Специальные символы C#](#c-special-characters)
  - [Директивы препроцессора C#](#c-preprocessor-directives)
  - [Общий синтаксис](#general-syntax)
  - [Комментарии](#comments)
  - [Консольное приложение C# Hello World](#c-hello-world-console-application)
  - [Переменные С#](#c-variables)
  - [Соглашения об именах C#](#c-naming-conventions)
    - [Терминология](#terminology)
    - [Таблица результатов](#summary-table)
  - [Типы данных C#](#c-data-types)
    - [Значимые типы](#value-types)
      - [Простые типы данных](#simple-data-types)
        - [Байты](#bytes)
        - [Беззнаковые целые числа](#unsigned-integers)
        - [Целые числа со знаком](#signed-integers)
        - [Типы с плавающей запятой](#floating-point-types)
        - [Символы Юникода](#unicode-characters)
        - [Логические](#booleans)
      - [Типы перечислений](#enum-types)
      - [Типы структур](#structure-types)
      - [Типы кортежей](#tuple-types)
      - [Значимые типы, допускающие значение NULL](#nullable-value-types)
    - [Ссылочные типы](#reference-types)
      - [Встроенные ссылочные типы](#built-in-reference-types)
        - [Типы объектов](#object-types)
        - [Типы строк](#string-types)
        - [Типы делегатов](#delegate-types)
      - [Типы интерфейсов](#interface-types)
      - [Ссылочные типы, допускающие значение NULL](#nullable-reference-types)
      - [Типы массивов](#array-types)
        - [Массив простых типов](#array-of-simple-types)
        - [Зубчатые массивы](#jagged-arrays)
        - [Свойства и методы массива](#array-properties--methods)
  - [Приведение типов](#type-casting)
    - [Неявное приведение типов](#implicit-casting)
    - [Явное приведение типов](#explicit-casting)
    - [Методы преобразования типов](#type-conversion-methods)
  - [Операторы](#operators)
    - [Арифметические операторы](#arithmetic-operators)
    - [Комбинированные операторы присваивания](#combined-assignment-operators)
    - [Операторы инкремента и декремента](#increment-and-decrement-operators)
    - [Операторы сравнения](#comparison-operators)
    - [Логические операторы](#logical-operators)
    - [Побитовые операторы](#bitwise-operators)
    - [Прецеденты операторов](#operator-precedents)
  - [Синтаксические конструкции](#statements)
    - [Условия](#conditions)
      - [**```if```**...**```else if```**...**```else```**](#ifelse-ifelse)
      - [**```switch```**](#switch-case)
    - [Циклы](#loops)
      - [Цикл **```while```**](#while-loop)
      - [Цикл **```do```**...**```while```**](#dowhile-loop)
      - [Цикл **```for```**](#for-loop)
      - [Цикл **```foreach```**](#foreach-loop)
    - [Конструкция **```goto```**](#goto-statement)
    - [Конструкция **```return```**](#return-statement)
    - [Конструкция **```yield```**](#yield-statement)
    - [Конструкция **```checked```** и **```unchecked```**](#checked-and-unchecked-statements)
    - [Конструкция **```lock```**](#lock-statement)
    - [Конструкция **```using```**](#using-statement)
    - [Обработка исключений](#exception-handling)
  - [Классы и объекты](#classes--objects)
    - [Члены](#members)
    - [Конструкторы](#constructors)
    - [Ключевое слово ```this```](#the-this-keyword)
    - [Сборщик мусора](#garbage-collector)
    - [Деструкторы/Финализаторы](#destructors--finalizers)
  - [Объектно-ориентированное программирование (ООП)](#object-oriented-programming-oop)
    - [Инкапсуляция/уровни доступа](#encapsulation--access-levels)
    - [Наследование](#inheritance)
    - [Полиморфизм/переопределение членов](#polymorphism--redefining-members)
    - [Модификатор static](#static)
    - [Свойства](#properties)
    - [Индексаторы](#indexers)
    - [Абстракция](#abstraction)
      - [Абстрактные классы и методы](#abstract-classes--methods)
      - [Интерфейсы](#interfaces)
    - [Пространства имен](#namespaces)
    - [Перегрузка операторов](#operator-overloading)
  - [Делегаты](#delegates)
    - [Анонимные методы](#anonymous-methods)
    - [Лямбда-выражения](#lambda-expressions)
  - [События](#events)
  - [Обобщения](#generics)
  - [Обобщенные коллекции](#generic-collections)
    - [List](#list)
    - [SortedList](#sortedlist)
    - [BitArray](#bitarray)
    - [Stack](#stack)
    - [Queue](#queue)
    - [Dictionary](#dictionary)
    - [HashSet](#hashset)
  - [Константы](#constants)
    - [Ключевое слово ```const```](#the-const-keyword)
    - [Ключевое слово ```readonly```](#the-readonly-keyword)
  - [Асинхронные методы](#asynchronous-methods)
  - [Работа с файлами](#working-with-files)
  - [Интегрированный язык запросов (LINQ)](#language-integrated-query-linq)
  - [Атрибуты](#attributes)
    - [Предопределенные атрибуты](#predefined-attributes)
    - [Пользовательские атрибуты](#custom-attributes)
  - [Полезные ссылки](#references)
  - [Титры](#credits)

---

## О шпаргалке {#about}

- Цель этой шпаргалки по C# — предоставить общие сведения о синтаксисе языка.
- HTML-версия этого документа размещена по адресу: https://constructg.com/csharp-cheat-sheet/
- Файл .md этой шпаргалки (оригинальная английская версия) размещен на [GitHub](https://github.com/LabinatorSolutions/csharp-cheat-sheet).
- Контрибуты, исправления багов, дополнения, и улучшения будут высоко оценены.
- Подготовлен [ConstructG.com](https://constructg.com/). Construct G — это онлайн-академия разработки игр.

## Введение в С#

### Что такое С#?

C# произносится как «Си-Шарп». Это объектно-ориентированный язык программирования, созданный Microsoft и работающий на .NET Framework. C# имеет корни из семейства C и близок к другим популярным языкам, таким как C++ и Java.

### Для чего используется C#?

- Приложения для работы с базами данных
- Приложения для персональных компьютеров
- Игры
- Мобильные приложения
- Приложения виртуальной реальности (VR)
- Веб-приложения
- Веб-разработка
- Веб-сервисы

**Для справки:**
https://en.wikipedia.org/wiki/C_Sharp_(programming_language)
https://docs.microsoft.com/en-us/dotnet/csharp/getting-started/

---

## Ключевые слова С#

### Зарезервированные ключевые слова

Ключевые слова — это предопределенные зарезервированные идентификаторы, которые имеют особое значение для компилятора.

- abstract
- as
- base
- bool
- breakbyte
- case
- catch
- char
- checked
- class
- const
- continue
- decimal
- default
- delegate
- do
- double
- else
- enum
- event
- explicit
- extern
- false
- finally
- fixed
- float
- for
- foreach
- goto
- if
- implicit
- in
- int
- interface
- internal
- is
- lock
- long
- namespace
- new
- null
- object
- operator
- out
- override
- params
- private
- protected
- public
- readonly
- ref
- return
- sbyte
- sealed
- short
- sizeof
- stackalloc
- static
- string
- struct
- switch
- this
- throw
- true
- try
- typeof
- uint
- ulong
- unchecked
- unsafe
- ushort
- using
- virtual
- void
- volatile
- while

### Контекстные ключевые слова

Контекстное ключевое слово используется для придания определенного значения в коде, но оно не является зарезервированным словом в C#. Некоторые контекстные ключевые слова, такие как «partial» и «where», имеют особое значение в двух или более контекстах.

- add
- alias
- ascending
- async
- await
- by
- descending
- dynamic
- equals
- from
- get
- global
- group
- into
- join
- let
- nameof
- notnull
- on
- orderby
- partial (метод)
- partial (тип)
- remove
- select
- set
- unmanaged (ограничение общего типа)
- value
- var
- when (состояние фильтра)
- where (ограничение общего типа)
- where (пункт запроса LINQ)
- yield

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/

---

## Специальные символы C#

Специальные символы — это предопределенные контекстные символы, которые изменяют элемент программы (литеральную строку, идентификатор или имя атрибута), к которому они добавляются. C# поддерживает следующие специальные символы:

- **@**, символ дословного идентификатора.
- **$**, интерполированный строковый символ.

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/tokens/

---

## Директивы препроцессора C#

Препроцессор - это программа, которая выполняет обработку исходного кода до его компиляции. 
Директивы препроцессора - это инструкции, которые сообщают препроцессору, как обрабатывать исходный код.

В C# есть следующие директивы препроцессора:

- \#if: начинает блок условной компиляции.
- \#else: определяет альтернативный блок условной \компиляции, который выполняется, если условие #if не \выполняется.
- \#elif: определяет дополнительное условие для блока \условной компиляции.
- \#endif: завершает блок условной компиляции.
- \#define: определяет макрос, который может быть \использован для замены текста в исходном коде.
- \#undef: отменяет определение макроса.
- \#warning: выводит предупреждение во время компиляции.
- \#error: выводит сообщение об ошибке во время компиляции.
- \#line: изменяет номер строки исходного кода, который \будет использоваться для отладки.
- \#region: начинает блок кода, который может быть свернут \или развернут в редакторе кода.
- \#endregion: завершает блок кода, начатый с помощью \#region.
- \#pragma: используется для указания специфических \инструкций компилятору.
- \#pragma warning: управляет выводом предупреждений \компилятора.
- \#pragma checksum: добавляет контрольную сумму в сборку для проверки целостности.

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/preprocessor-directives/

---

## Общий синтаксис

- Учитывает регистр.
- Код набирается внутри блоков кода **\{}**
- Завершение строки осуществляется с помощью точки с запятой **;**

---

## Комментарии

- Однострочные комментарии набираются внутри двух косых черт:

```csharp
// Однострочный комментарий
```

- Многострочные комментарии набираются через косую черту, за которой следует звездочка. Закрывается он звездочкой, за которой следует косая черта.

```csharp
/*
  Это многострочный комментарий.
  Это вторая строка комментария.
*/
```

---

## Консольное приложение "Hello World"

```csharp
class Hello
{
    static void Main(string[] args)
    {
        System.Console.WriteLine("Hello World!");
    }
}
```

**Примечание:** Исходные файлы C# обычно имеют расширение файла **.cs**

---

## Переменные С#

**Синтаксис:**

```
<модификатор> <тип_данных> <имя_переменной> = <начальное_значение>;
```

- Имя переменной должно начинаться с буквы или символа подчеркивания.
- Имя переменной не может начинаться с цифры.
- Имя переменной должно содержать только буквы, цифры и символ подчеркивания.
- Имя переменной не может содержать пробелы.
- Имя переменной должно быть описательным и отражать ее назначение.
- Имя переменной должно быть уникальным в пределах области видимости, в которой она определена.

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/language-specification/variables

---

## Соглашения об именах C#

### Терминология

Для описания стандартов именования C# и .NET используются следующие три терминологии.

- **Camel Case (camelCase):** В этом стандарте первая буква слова всегда пишется с маленькой буквы, а после этого каждое слово начинается с заглавной буквы.
- **Pascal Case (PascalCase):** Здесь первая буква каждого слова написана заглавной буквой.
- **Underscore Prefix (_underScore):** Для подчеркивания ( __ ), слово после _ используйте стандарт Camel Case.

### Таблица результатов

| Типы и поля     | Стандарт написания |
| --------------- | --------------- |
| Private Field   | _lowerCamelCase |
| Protected Field | UpperCamelCase  |
| Internal Field  | UpperCamelCase  |
| Constant        | UpperCamel Case |
| Property        | UpperCamelCase  |
| Method          | UpperCamelCase  |
| Class           | UpperCamelCase  |
| Interface       | IUpperCamelCase |
| Local Variable  | lowerCamelCase  |
| Parameter       | lowerCamelCase  |

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/inside-a-program/coding-conventions
https://google.github.io/styleguide/csharp-style.html
https://www.dofactory.com/reference/csharp-coding-standards

---

## Типы данных C#

### Типы значений

**Для справки:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/value-types

#### Простые типы данных

**Для справки:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/integral-numeric-types

##### Байты

```csharp

byte myUnsignedByte = 8; // Размер: 8 bits  | Диапазон: 0 to 255
sbyte mySignedByte = -8; // Размер: 8 bits  | Диапазон: -128 to +127
```

##### Беззнаковые целые числа

```csharp

ushort myUnsignedShort = 16; // Размер: 16 bits  | Диапазон: 0 to 65535
uint myUnsignedInt = 32; // Размер: 32 bits  | Диапазон: 0 to 2^32-1
ulong myUnsignedLong = 64; // Размер: 64 bits  | Диапазон: 0 to 2^64-1
```

##### Целые числа со знаком

```csharp
short mySignedShort = 16; // Размер: 16 bits  | Диапазон: -32768 to +32767
int mySignedInt = 32; // Размер: 32 bits  | Диапазон: -2^31  to +2^31-1
long mySignedLong = -64; // Размер: 64 bits  | Диапазон: -2^63  to +2^63-1
```

##### Типы с плавающей запятой

```csharp
float myFloat = 3.14F; // Размер: 32 bits  | Диапазон: 7 digits of precision
double myDouble = 3.14D; // Размер: 64 bits  | Диапазон: 15-16 digits of precision
decimal myDecimal = 3.14M; // Размер: 128 bits | Диапазон: 28-29 digits of precision
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/floating-point-numeric-types

##### Символы Юникода

```csharp
char myChar = 'a'; // Размер: 16 bits  | Диапазон: Unicode character
```

##### Логические

```csharp
bool myBool = true; // Размер: 4 bits   | Диапазон: true or false
```

#### Типы перечислений

Тип перечисления — это отдельный значимый тип с набором именованных констант.

```csharp
using System;

enum Color
{
    Red,
    Green,
    Blue
}

class Test
{
    static void PrintColor(Color color)
    {
        switch (color)
        {
            case Color.Red:
                Console.WriteLine("Red");
                break;
            case Color.Green:
                Console.WriteLine("Green");
                break;
            case Color.Blue:
                Console.WriteLine("Blue");
                break;
            default:
                Console.WriteLine("Unknown color");
                break;
        }
    }

    static void Main(string[] args)
    {
        Color c = Color.Red;
        PrintColor(c);
        PrintColor(Color.Blue);
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/enum

#### Типы структур

Подобно классам, структуры - это структуры данных, которые могут содержать элементы данных и функции-члены, но в отличие от классов, структуры являются типами значений и не требуют выделения кучи. Переменная типа struct непосредственно хранит данные структуры, тогда как переменная типа class хранит ссылку на динамически выделяемый объект. Типы Struct не поддерживают указанное пользователем наследование, и все типы struct неявно наследуются от типа object.

Структуры особенно полезны для небольших структур данных, имеющих семантику значений. Комплексные числа, точки в системе координат или пары ключ-значение в словаре - все это хорошие примеры структур. Использование структур, а не классов, для небольших структур данных может существенно повлиять на количество выделений памяти, выполняемых приложением.

```csharp
struct Point
{
    public int x, y;

    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/struct

#### Типы кортежей

Функция кортежей, доступная в C# 7.0 и более поздних версиях, предоставляет краткий синтаксис для группировки нескольких элементов данных в упрощенную структуру данных.

```csharp
(double, int) t1 = (4.5, 3);
Console.WriteLine($"Кортеж с элементами {t1.Item1} and {t1.Item2}."); // Выход => Кортеж с элементами 4.5 и 3.

(double Sum, int Count) t2 = (4.5, 3);
Console.WriteLine($"Сумма {t2.Count} элементов равна {t2.Sum}."); // Выход => Сумма 3 элементов равна 4,5.
```

**Learn More:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/value-tuples

#### Типы значений, допускающие значение NULL

Значение с возможностью обнуления типа **``T?``** представляет все значения его базового типа значений **T** и дополнительное значение null. Например, вы можете присвоить переменной **``bool?``** любое из следующих трех значений: true, false или null. Базовый тип значения **T** сам по себе не может быть типом значения с возможностью присвоить ему null.

```csharp
int? b = 10;

if (b.HasValue)
{
    Console.WriteLine($"b это {b.Value}");
}

else
{
    Console.WriteLine("b не имеет значения");
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/nullable-value-types

### Ссылочные типы

#### Встроенные ссылочные типы

##### Типы объектов

Тип объекта является псевдонимом System.Object в .NET. В унифицированной системе типов C# все типы, предопределенные и определяемые пользователем, ссылочные типы и типы значений, наследуются прямо или косвенно от System.Объект. Вы можете присваивать значения любого типа переменным типа object. Любой объектной переменной можно присвоить значение по умолчанию, используя литерал null.

##### Типы строк

Принято думать о строках как о массивах символов. На самом деле строки в C# являются объектами.
Когда вы объявляете строковую переменную, вы, по сути, создаете экземпляр объекта типа String.

```csharp
string fooString = "\"экранируйте\" кавычки и добавьте \n (новые строки) and \t (табуляции)";
Console.WriteLine(fooString);

// Вы можете получить доступ к каждому символу строки с помощью индексатора:
char charFromString = fooString[1]; // => 'e'

// Строки неизменяемы: вы не сможете сделать этого fooString[1] = 'X';

// Сравнивайте строки с текущей культурой, игнорируя регистр
string.Compare(fooString, "x", StringComparison.CurrentCultureIgnoreCase);

// Форматирование, основанное на sprintf
string fooFs = string.Format("Check Check, {0} {1}, {0} {1:0.0}", 1, 2);

// Даты и форматирование
DateTime fooDate = DateTime.Now;
Console.WriteLine(fooDate.ToString("hh:mm, dd MMM yyyy"));

// Интерполяция строк
string myName = "Jane Doe";
Console.WriteLine($"My name is: {myName}. It is great to be here!");

// String Builder
StringBuilder sb = new StringBuilder();
sb.Append("Hello ");
sb.AppendLine("World!");
Console.WriteLine(sb);

// Дословная строка
// Вы можете использовать символ @ перед строковым литералом, чтобы экранировать все символы в строке
string path = "C:\\Users\\User\\Desktop";
string verbatimPath = @"C:\Users\User\Desktop";
Console.WriteLine(path == verbatimPath);  // => true

// You can split a string over two lines with the @ symbol. Чтобы избежать " использования ""
string bazString = @"Here's some stuff
on a new line! ""Wow!"", the masses cried";

// Популярные строковые методы и свойства
string myText = "some text";

Console.WriteLine(myText.IndexOf('t')); // Outputs => 5

myText = myText.Insert(0, "This is ");
Console.WriteLine(myText); // Outputs => "This is some text"

myText = myText.Replace("This is", "Here is");
Console.WriteLine(myText); // Outputs => "Here is some text"

if(myText.Contains("some"))
Console.WriteLine("found"); // Outputs "found"

myText = myText.Remove(4);
Console.WriteLine(myText); // Outputs "Here"

myText = myText.Substring(2, 3);
Console.WriteLine(myText); // Outputs "re"
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/strings/

##### Типы делегатов

Тип делегата представляет ссылки на методы с определенным списком параметров и типом возвращаемого значения. Делегаты позволяют рассматривать методы как сущности, которые могут быть назначены переменным и переданы в качестве параметров. Делегаты аналогичны концепции указателей на функции, встречающейся в некоторых других языках, но, в отличие от указателей на функции, делегаты объектно-ориентированы и типобезопасны.

```csharp
using System;

delegate double Function(double x);

class Multiplier
{
    double factor;

    public Multiplier(double factor)
    {
        this.factor = factor;
    }

    public double Multiply(double x)
    {
        return x * factor;
    }
}

class Test
{
    static double Square(double x)
    {
        return x * x;
    }

    static double[] Apply(double[] a, Function f)
    {
        double[] result = new double[a.Length];
        for (int i = 0; i < a.Length; i++)
        {
          result[i] = f(a[i]);
        }
        return result;
    }

    static void Main(string[] args)
    {
        double[] a = {0.0, 0.5, 1.0};
        double[] squares = Apply(a, Square);
        double[] sines = Apply(a, Math.Sin);

        Multiplier m = new Multiplier(2.0);
        double[] doubles =  Apply(a, m.Multiply);
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/delegates/

#### Типы интерфейсов

Интерфейс определяет контракт, который может быть реализован классами и структурами. Интерфейс может содержать методы, свойства, события и индексаторы. Интерфейс не предоставляет реализации определяемых им элементов — он просто указывает элементы, которые должны предоставляться классами или структурами, реализующими интерфейс. Интерфейсы могут использовать множественное наследование.

```csharp
public interface IShape
{
  void Draw();
}
class Circle : IShape
{
    public void Draw()
    {
      Console.WriteLine("Рисуем круг");
    }
}
static void Main(string[] args)
{
    IShape c = new Circle();
    c.Draw(); // Выводит "Рисуем круг"
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/interfaces/
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/interface

#### Типы ссылок, допускающие значение NULL

Обнуляемые ссылочные типы доступны, начиная с C# 8.0, в коде, который выбрал контекст, поддерживающий обнуление. Обнуляемые ссылочные типы, предупреждения статического анализа null и оператор, не допускающий обнуления, являются необязательными языковыми функциями. По умолчанию все они отключены. Контекст с возможностью обнуления контролируется на уровне проекта с помощью настроек сборки или в коде с помощью прагм.

```csharp
string notNull = "Hello";
string? nullable = default;
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/nullable-reference-types

#### Типы массивов

Массив - это структура данных, содержащая ряд переменных, доступ к которым осуществляется через вычисляемые индексы. Переменные, содержащиеся в массиве, также называемые элементами массива, все имеют один и тот же тип, и этот тип называется типом элемента массива.

Типы массивов являются ссылочными типами, и объявление переменной массива просто выделяет место для ссылки на экземпляр массива. Фактические экземпляры массива создаются динамически во время выполнения с использованием оператора new. Операция new определяет длину нового экземпляра массива, которая затем фиксируется на время существования экземпляра. Индексы элементов массива варьируются от 0 до Length - 1. Оператор new автоматически инициализирует элементы массива их значением по умолчанию, которое, например, равно нулю для всех числовых типов и null для всех ссылочных типов.

##### Массив простых типов

```csharp
int[] a1   = new int[10];        // Одномерный массив
int[,] a2  = new int[10, 5];     // Двумерный массив
int[,,] a3 = new int[10, 5, 2];  // Трехмерный массив
```

##### Зубчатые массивы

**Зубчатый массив:** представляет собой массив с элементами типа array.

**Синтаксис:**

```
data_type[][] name_of_array = new data_type[rows][]
```

**Пример 1:**

```csharp
int[][] jaggedArray = new int[3][]; // Зубчатый массив
jaggedArray[0] = new int[10];
jaggedArray[1] = new int[5];
jaggedArray[2] = new int[20];
```

**Пример 2:**

```csharp
int[][] anotherJaggedArray = new int[][] // Другой способ объявить зубчатые массивы
{
    new int[] {1,8,2,7,9},
    new int[] {2,4,6},
    new int[] {33,42}
};

int x = anotherJaggedArray[2][1];
Console.WriteLine(x); // Вывод => 42
```

##### Свойства и методы массива

Класс Array в C# предоставляет различные свойства и методы для работы с массивами.

Класс Array реализует интерфейс **IEnumerable**, поэтому вы можете использовать методы расширения LINQ**, такие как Max(), Min(), Sum(), Average() и многие другие.

```csharp
using System;
using System.Linq;

public class Program
{
    public static void Main(string[] args)
    {
        int[] integersArray = new int[5]{80, 20, 35, 18, 9};

        Console.WriteLine(integersArray.Max());
        Console.WriteLine(integersArray.Min());
        Console.WriteLine(integersArray.Sum());
        Console.WriteLine(integersArray.Average());
    }
}
```

Класс **System.Array** также включает методы для создания массивов, манипулирования ими, поиска и сортировки.

```csharp
using System;

public class Program
{
    public static void Main(string[] args)
    {
        int[] integersArray = {20, 9, 16, 50, 3};

        Console.WriteLine("Original Array:");
        foreach(int element in integersArray)
        {
            Console.WriteLine(element);
        }

        Console.WriteLine("Sorted Array:");
        Array.Sort(integersArray);
        foreach(int element in integersArray)
        {
            Console.WriteLine(element);
        }

        Console.WriteLine("Reversed Array:");
        Array.Reverse(integersArray);
        Array.ForEach<int>(integersArray, n => Console.WriteLine(n));

        Console.WriteLine(Array.BinarySearch(integersArray, 9));
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/arrays/
https://docs.microsoft.com/en-us/dotnet/api/system.array
https://docs.microsoft.com/en-us/dotnet/api/system.linq.enumerable

---

## Приведение типов

Приведение типов - это когда вы присваиваете значение одного типа данных другому типу.

В C# существует два типа приведения:

**Неявное приведение (автоматически)** - преобразование меньшего типа в больший размер типа

> char -> int -> long -> float -> double

**Явное приведение (вручную)** - преобразование типа большего размера в тип меньшего размера:

> double -> float -> long -> int -> char

### Неявное приведение

Неявное приведение выполняется автоматически при передаче типа меньшего размера в тип большего размера.

```csharp
int myInt = 9;
double myDouble = myInt;       // Автоматическое приведение: int в double

Console.WriteLine(myInt);      // Выводит 9
Console.WriteLine(myDouble);   // Выводит 9
```

### Явное приведение типов

Явное приведение должно быть выполнено вручную путем помещения типа в круглые скобки перед значением.

```csharp
double myDouble = 9.78;
int myInt = (int) myDouble;    // Явное приведение: double к int

Console.WriteLine(myDouble);   // Выводит 9.78
Console.WriteLine(myInt);      // Выводит 9
```

### Методы преобразования типов

Также возможно явно преобразовывать типы данных с помощью встроенных методов.

- ToBoolean
- ToByte
- ToChar
- ToDateTime
- ToDecimal
- ToDouble
- ToInt16
- ToInt32
- ToInt64
- ToSbyte
- ToSingle
- ToString
- ToType
- ToUInt16
- ToUInt32
- ToUInt64

```csharp
int myInt = 10;
double myDouble = 5.25;
bool myBool = true;

Console.WriteLine(Convert.ToString(myInt));    // преобразовать int в string
Console.WriteLine(Convert.ToDouble(myInt));    // преобразовать int в double
Console.WriteLine(Convert.ToInt32(myDouble));  // преобразовать double в int
Console.WriteLine(Convert.ToString(myBool));   // преобразовать bool в string
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/types/casting-and-type-conversions

---

## Операторы

### Арифметические операторы

```csharp
float myFloat = 0;

myFloat = 3 + 2; // Сложение       => 5
myFloat = 3 - 2; // Вычитание    => 1
myFloat = 3 * 2; // Умножение => 6
myFloat = 3 / 2; // Деление       => 1
myFloat = 3 % 2; // Деление по модулю        => 1

/*
    Обратите внимание, что знак деления дает неверный результат.
Это связано с тем, что он оперирует двумя целыми значениями и, следовательно, округляет результат и возвращает целое число.
Чтобы получить правильное значение, одно из чисел необходимо преобразовать в число с плавающей запятой.
*/
myFloat = 3 / (float) 2; // 1.5
```

### Комбинированные операторы присваивания

```csharp
float myFloat = 0;

myFloat += 2; // myNumber = myNumber + 2
myFloat -= 2; // myNumber = myNumber - 2
myFloat *= 2; // myNumber = myNumber * 2
myFloat /= 2; // myNumber = myNumber / 2
myFloat %= 2; // myNumber = myNumber % 2
```

### Операторы инкремента и декремента

```csharp
int myCounter = 0;

Console.WriteLine(myCounter++); // Выводит "0", _myCounter = 1. Последующий инкремент
Console.WriteLine(++myCounter); // Выводит "2", _myCounter = 2. Предварительный инкремент
Console.WriteLine(myCounter--); // Выводит "2", _myCounter = 1. Последующий декремент
Console.WriteLine(--myCounter); // Выводит "0", _myCounter = 0. Предварительный декремент
```

### Операторы сравнения

```csharp
Console.WriteLine($"3 == 2? {3 == 2}"); // => false
Console.WriteLine($"3 != 2? {3 != 2}"); // => true
Console.WriteLine($"3 > 2? {3 > 2}"); // => true
Console.WriteLine($"3 < 2? {3 < 2}"); // => false
Console.WriteLine($"2 <= 2? {2 <= 2}"); // => true
Console.WriteLine($"2 >= 2? {2 >= 2}"); // => true
```

### Логические операторы

```csharp
bool myBool;

myBool = (true && false); // Логическое И => (false)
myBool = (true || false); // Логическое ИЛИ  => (true)
myBool = !(true); // Логическое НЕ => (false)

Console.WriteLine(myBool);
```

### Побитовые операторы

```csharp
int myInteger;

// Побитовые операторы могут манипулировать отдельными битами внутри целого числа.

myInteger = 5 & 4; // И (0b101 & 0b100 = 0b100 = 4)
myInteger = 5 | 4; // ИЛИ (0b101 | 0b100 = 0b101 = 5)
myInteger = 5 ^ 4; // Исключающее ИЛИ (0b101 ^ 0b100 = 0b001 = 1)
myInteger = 4 << 1; // сдвиг влево (0b100 << 1 = 0b1000 = 8)
myInteger = 4 >> 1; // сдвиг вправо (0b100 >> 1 = 0b10 = 2)
myInteger = ~ 4; // инвертирование (~0b00000100 = 0b11111011 = -5)

// Эти побитовые операторы имеют сокращенные операторы присваивания, точно так же, как арифметические операторы.

myInteger = 5;
myInteger &= 4; // И (0b101 & 0b100 = 0b100 = 4)

myInteger = 5;
myInteger |= 4; // ИЛИ (0b101 | 0b100 = 0b101 = 5)

myInteger = 5;
myInteger ^= 4; // Исключающее ИЛИ (0b101 ^ 0b100 = 0b001 = 1)

myInteger = 5;
myInteger <<= 1; // сдвиг влево (0b101 << 1 = 0b1010 = 10)

myInteger = 5;
myInteger >>= 1; // сдвиг вправо (0b101 >> 1 = 0b10 = 2)
```

### Прецеденты операторов

```csharp
/*

- круглые скобки ()

- Постфиксный инкремент и декремент           ++, --
- Префиксный инкремент, декремент и унарный   ++, --, +, -, !, ~

- Умножение, деление, деление по модулю       *, /, %
- Сложение, вычитание                         +, -
                                              
- Сдвиг                                       <<, >>
- Реляционный                                 <, <=, >, >=
- Равенство                                   ==, !=
                                              
- Побитовое И                                 &
- Побитовое исключающее ИЛИ                   ^
- Побитовое ИЛИ                               |
                                              
- Логическое И                                &&
- Логическое ИЛИ                              ||
                                              
- Тернарный                                   ? :
- Назначение                                  =, +=, -=, *=, /=, %=, &=, |=, ^=, <<=, >>=

*/
```

Чем выше приоритет оператора, тем выше он отображается в таблице.

Для большей ясности можно использовать круглые скобки (), чтобы указать, какая часть выражения будет вычислена первой. Круглые скобки имеют наибольший приоритет из всех операторов.

```csharp
int myInteger;

myInteger = 4 + 6 / 2;   // => 7
myInteger = (4 + 6) / 2; // => 5
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/

---

## Конструкции

### Условия

#### **```if```**...**```else if```**...**```else```**
```csharp
int time = 22;

if (time < 10)
{
  Console.WriteLine("Доброе утро.");
}
else if (time < 20)
{
  Console.WriteLine("Добрый день.");
}
else
{
  Console.WriteLine("Добрый вечер.");
}

// Тернарные операторы
// Простое if/else можно записать следующим образом:
// <условие> ? <true> : <false>
int toCompare = 17;
string isTrue = toCompare == 17 ? "True" : "False";
```

#### **```switch```** Case

```csharp
// Переключатель (switch) работает с типами данных byte, short, char и int.
// Он также работает с перечислимыми типами (обсуждается в Enum Types),
// классом String и несколькими специальными классами, оборачивающими
// примитивные типы: Character, Byte, Short и Integer.

int month = 3;
string monthString;
switch (month)
{
    case 1:
        monthString = "January";
        break;
    case 2:
        monthString = "February";
        break;
    case 3:
        monthString = "March";
        break;
    // Вы можете назначить более одного случая для действия.
    // Однако нельзя добавить действие без оператора break перед другим случаем
    // (если вы хотите сделать это, вам придется явно добавить goto case x).
    case 6:
    case 7:
    case 8:
        monthString = "Summer time!!";
        break;
    default:
        monthString = "Some other month";
        break;
}
```

### Циклы

#### Цикл **```while```**

```csharp

int fooWhile = 0;

while (fooWhile < 100)
{
    // Iterated 100 times, fooWhile 0->99
    fooWhile++;
}
```

#### Цикл **```do```**...**```while```**

```csharp
// Do While Loop
int fooDoWhile = 0;

do
{
    // Start iteration 100 times, fooDoWhile 0->99
    if (false)
    {
        continue; // skip the current iteration
    }

    fooDoWhile++;

    if (fooDoWhile == 50)
    {
        break; // breaks from the loop completely
    }

} while (fooDoWhile < 100);
```

#### Цикл **```for```**

```csharp
for (int fooFor = 0; fooFor < 10; fooFor++)
{
    // Iterated 10 times, fooFor 0->9
}
```

#### Цикл **```foreach```**

```csharp
foreach (char character in "Hello World".ToCharArray())
{
    // Iterated over all the characters in the string
}
```

### Оператор безусловного перехода **```goto```**

Оператор безусловного перехода goto используется для передачи управления программы к определенной метке (метка - это идентификатор, представляющий собой метку в программе). 

```csharp
static void Main(string[] args) {
    int i = 0;
    goto check;

    loop:
    Console.WriteLine(args[i++]);

    check:
    if (i < args.Length)
    {
      goto loop;
    }
}
```

### Оператор **```return```**

```csharp
static int Add(int a, int b)
{
    return a + b;
}

static void Main(string[] args)
{
    Console.WriteLine(Add(1, 2));
    return;
}
```

### Оператор **```yield```**

```csharp
static IEnumerable<int> Range(int from, int to)
{
    for (int i = from; i < to; i++)
    {
        yield return i;
    }
    yield break;
}

static void Main(string[] args)
{
    foreach (int x in Range(-10,10))
    {
        Console.WriteLine(x);
    }
}
```

Этот код на C# определяет метод `Range`, который создает итератор для генерации последовательности целых чисел от заданного значения `from` до `to`. Затем метод `Main` использует этот итератор для вывода чисел от -10 до 9 включительно с помощью цикла `foreach` и `Console.WriteLine`. Оператор `yield return` позволяет лениво генерировать значения по мере необходимости, что может быть полезным для больших последовательностей данных.

### Операторы **```checked```** and **```unchecked```**

```csharp
static void Main(string[] args)
{
    int i = int.MaxValue;
    checked
    {
        Console.WriteLine(i + 1);        // Exception
    }
    unchecked
    {
        Console.WriteLine(i + 1);        // Overflow
    }
}
```

Этот код в C# иллюстрирует использование ключевых слов `checked` и `unchecked` для контроля переполнения при выполнении арифметических операций. В блоке `checked`, операция `int.MaxValue + 1` вызывает `System.OverflowException`. В блоке `unchecked`, хотя происходит переполнение, оно не вызывает исключение, и результат обрезается, становясь минимальным значением типа `int`.

### Оператор **```lock```** 

```csharp
class Account
{
    decimal balance;
    public void Withdraw(decimal amount)
    {
        lock (this)
        {
            if (amount > balance)
            {
                throw new Exception("Insufficient funds");
            }
            balance -= amount;
        }
    }
}
```

Этот код представляет класс `Account` с полем `balance`, представляющим баланс счета. Метод `Withdraw` выполняет снятие денег с учетом блокировки (`lock`), чтобы обеспечить потокобезопасность при изменении баланса. Если запрашиваемая сумма (`amount`) превышает текущий баланс, генерируется исключение `Exception` с сообщением "Insufficient funds". В противном случае запрашиваемая сумма вычитается из баланса.

### Оператор **```using```**

```csharp
static void Main(string[] args)
{
    using (TextWriter w = File.CreateText("test.txt"))
    {
        w.WriteLine("Line one");
        w.WriteLine("Line two");
        w.WriteLine("Line three");
    }
}
```

Этот код создает и использует объект `TextWriter` для записи строк в файл "test.txt". С помощью конструкции `using` обеспечивается автоматическое закрытие файла после завершения блока кода. В результате выполнения программы в файле "test.txt" будут записаны три строки: "Line one", "Line two" и "Line three".

### Обработка исключений

```csharp
static double Divide(double x, double y)
{
    if (y == 0)
    {
      throw new DivideByZeroException();
    }
    return x / y;
}

static void Main(string[] args)
{
    try
    {
        if (args.Length != 2)
        {
            throw new Exception("Two numbers are required");
        }
        double x = double.Parse(args[0]);
        double y = double.Parse(args[1]);
        Console.WriteLine(Divide(x, y));
    }

    catch (Exception e)
    {
        Console.WriteLine(e.Message);
    }

    finally
    {
        Console.WriteLine("Terminating!");
    }
}
```

Этот код на C# определяет функцию `Divide`, которая выполняет деление двух чисел, и в методе `Main` использует механизм обработки исключений для проверки ввода и обработки возможных ошибок. Если количество аргументов командной строки не равно двум, генерируется исключение с сообщением "Two numbers are required". Затем происходит парсинг аргументов в тип `double`, и если делитель (`y`) равен нулю, генерируется исключение `DivideByZeroException`. В блоке `finally` выводится сообщение "Terminating!", которое будет выполнено в любом случае, даже если произойдет исключение или не произойдет.

**Learn More:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/statements-expressions-operators/statements

---

## Классы и объекты

Классы — это наиболее фундаментальные типы в C#. Класс — это структура данных, которая объединяет состояние (поля) и действия (методы и другие члены функций) в единое целое. Класс предоставляет определение для динамически создаваемых экземпляров класса, также известных как объекты. Классы поддерживают наследование и полиморфизм, механизмы, с помощью которых производные классы могут расширять и специализировать базовые классы.

Новые классы создаются с помощью объявлений классов. Объявление класса начинается с заголовка, который определяет атрибуты и модификаторы класса, имя класса, базовый класс (если он есть) и интерфейсы, реализуемые классом. Заголовок следует за телом класса, которое состоит из списка объявлений членов, записанных между ограничителями `{` и `}`.

Приведенный ниже пример демонстрирует класс с конструктором и деструктором.

```csharp
using System;

namespace Example
{
  class Complex
  {
      private int realNum, imaginaryNum;

      // Определение конструктора
      public Complex()
      {
          realNum = 0;
          imaginaryNum = 0;
      }

      // Метод SetValue устанавливает значения действительной и мнимой частей.
      public void SetValue(int r, int i)
      {
          realNum = r;
          imaginaryNum = i;
      }

      // Метод DisplayValue отображает значения действительной и мнимой частей.
      public void DisplayValue()
      {
          Console.WriteLine("Real = " + realNum);
          Console.WriteLine("Imaginary = " + imaginaryNum);
      }

      // Определение деструктора для класса Complex.
      ~Complex()
      {
          Console.WriteLine("Destructor was called");
      }

  }

  class Program
  {
      static void Main(string[] args)
      {
          // Создание экземпляра класса Complex C вызывает конструктор.
          Complex myComplexNumber = new Complex();

          // Вызов метода SetValue с использованием экземпляра C. Установка значений для действительной части в 2 и мнимой в 3.
          myComplexNumber.SetValue(2, 3);

          // Отображение значений действительной и мнимой частей.
          myComplexNumber.DisplayValue();
      }
  }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/classes
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/objects

### Члены

Члены класса могут быть либо статическими, либо экземплярными. Статические члены принадлежат классам, а экземплярные члены принадлежат объектам (экземплярам классов).

В следующей таблице предоставлен обзор видов членов, которые могут содержаться в классе.

| Член         | Описание                                                    |
| ------------ | ------------------------------------------------------------ |
| Константы    | Константные значения, связанные с классом                   |
| Поля         | Переменные класса                                           |
| Методы       | Вычисления и действия, которые может выполнять класс        |
| Свойства     | Действия, связанные с чтением и записью именованных свойств класса |
| Индексаторы  | Действия, связанные с индексированием экземпляров класса, подобно массиву |
| События      | Уведомления, которые может генерировать класс               |
| Операторы    | Преобразования и операторы выражений, поддерживаемые классом |
| Конструкторы | Действия, необходимые для инициализации экземпляров класса или самого класса |
| Деструкторы  | Действия, выполняемые перед окончательным удалением экземпляров класса |
| Типы         | Вложенные типы, объявленные классом                          |

### Конструкторы

Когда создается экземпляр класса или структуры, вызывается его конструктор. У класса или структуры может быть несколько конструкторов, принимающих разные аргументы. Конструкторы позволяют программисту устанавливать значения по умолчанию, ограничивать создание экземпляров и писать гибкий и читаемый код.

**Примечание:** При необходимости можно также цеплять и перегружать конструкторы.

```csharp
class MyRectangle
{
    public int x, y;

    public MyRectangle(int width, int height) // Defining the constructor
    {
        x = width;
        y = height;
    }

    static void Main(string[] args)
    {
        MyRectangle r = new MyRectangle(20, 15);
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/constructors

### Ключевое слово ```this```

Внутри конструктора, а также в других методах, принадлежащих объекту, можно использовать специальное ключевое слово, называемое ```this```. Это ключевое слово представляет собой ссылку на текущий экземпляр класса. Допустим, например, что параметры конструктора имеют те же имена, что и соответствующие поля. Тогда поля все равно могут быть доступны с использованием ключевого слова ```this```, даже если они перекрываются параметрами.

```csharp
class MyRectangle
{
    public int x, y;

    public MyRectangle(int x, int y)
    {
        this.x = x; // Set field x to parameter x
        this.y = y; // Set field y to parameter y
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/this

### Сборщик мусора

В .NET Framework есть сборщик мусора, который периодически освобождает память, используемую объектами, когда они больше не доступны. Это освобождает программиста от часто утомительной и ошибочной задачи ручного управления памятью.

Объект становится подлежащим уничтожению, когда на него больше нет ссылок.

**Примечание:** В C# объекты не могут быть явно деаллоцированы.

```csharp
static void Main(string[] args)
{
    if (true)
    {
        int myNum = 0;
    }
    // Integer myNum becomes inaccessible here and will be destroyed.
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/standard/garbage-collection/fundamentals

### Деструкторы / Финализаторы

Деструктор или финализатор используется для освобождения любых неуправляемых ресурсов, выделенных объектом. Он вызывается автоматически перед уничтожением объекта и не может быть вызван явно.

- У класса может быть только один деструктор.
- Деструкторы не могут быть вызваны явно. Они вызываются автоматически.
- Деструктор не принимает модификаторов и не имеет параметров.
- Имя деструктора точно такое же, как у класса, но с префиксом тильды (```~```).

```csharp
class Message
{
    public Message() // Defining the construtor
    {
        Console.WriteLine("The constructor is called");
    }

    ~Message() // Defining the desctructor
    {
        Console.WriteLine("The destructor is called");
    }
}

static void Main(string[] args)
{
    Message myMessage = new Message();
}
```

**Примечание:** Сборщик мусора в .NET Framework автоматически управляет выделением и освобождением памяти для объектов. Однако, когда класс использует неуправляемые ресурсы, такие как сетевые подключения, файлы и компоненты пользовательского интерфейса, следует использовать деструктор для освобождения этих ресурсов, когда они больше не нужны.

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/destructors

---

## Объектно-ориентированное программирование (ООП)

C# — это объектно-ориентированный язык. Четыре ключевых приёма, используемых в объектно-ориентированном программировании, это:

— **Абстракция** означает скрытие ненужных подробностей от потребителей типа.

— **Инкапсуляция** означает, что группа связанных свойств, методов и других членов рассматривается как единое целое.

— **Наследование** описывает возможность создания новых классов на основе существующего класса.

— **Полиморфизм** означает, что у вас может быть несколько классов, которые могут использоваться взаимозаменяемо, даже если каждый класс реализует одни и те же свойства или методы по-разному.

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/intro-to-csharp/object-oriented-programming

## Инкапсуляция / Уровни доступа

В программировании инкапсуляция означает не только объединение членов внутри класса, но и ограничение доступа к внутренним рабочим процессам этого класса.
Инкапсуляция реализуется с помощью модификаторов доступа. Модификатор доступа определяет область видимости и доступность члена класса.

У каждого члена класса есть связанный с ним уровень доступности, который контролирует области кода программы, имеющие доступ к члену. Существуют пять возможных форм доступности. Они представлены в следующей таблице.

| Модификатор доступа    | Значение                                                       |
| ------------------ | ------------------------------------------------------------- |
| public             | Доступ не ограничен                                           |
| protected           | Доступ ограничен этим классом или производными от этого класса |
| internal            | Доступ ограничен этой программой                               |
| protected internal  | Доступ ограничен этой программой или производными от этого класса |
| private             | Доступ ограничен этим классом                                 |

**Примечание:** При выборе уровня доступности обычно лучше использовать наиболее строгий уровень, допустимый в данном контексте.

| Доступность | Значение                                                       |
| ---------- | ------------------------------------------------------------- |
| События      | Уведомления, которые могут быть сгенерированы этим классом          |
| Операторы     | Конвертации и операторы выражений, поддерживаемые этим классом     |
| Конструкторы   | Действия, необходимые для инициализации экземпляров этого класса или самого класса |
| Деструкторы   | Действия, которые необходимо выполнить перед постоянным удалением экземпляров этого класса |
| Типы         | вложенные типы, объявленные этим классом                         |

## Наследование

Наследование позволяет классу наследовать свойства другого класса. Это позволяет определять класс на основе другого класса. Это упрощает создание и обслуживание приложений.

Класс, свойства которого наследуются другим классом, называется базовым классом.
Класс, который наследует свойства, называется производным классом.

**Примечание:** C# не поддерживает множественное наследование. Однако вы можете использовать интерфейсы для реализации множественного наследования.

```csharp
using System;

namespace RectangleApplication
{
    class Rectangle
    {
        protected double length;
        protected double width;

        public Rectangle(double l, double w)
        {
            length = l;
            width = w;
        }

        public double GetArea()
        {
            return length * width;
        }

        public void Display()
        {
            Console.WriteLine($"Length: {length}");
            Console.WriteLine($"Width: {width}");
            Console.WriteLine($"Area: {GetArea()}");
        }
   }

    class Tabletop : Rectangle
    {
        private double cost;
        public Tabletop(double l, double w) : base(l, w) { }

        public double GetCost()
        {
            double cost;
            cost = GetArea() * 70;

            return cost;
        }

        public void Display()
        {
            base.Display();
            Console.WriteLine($"Cost: {GetCost()}");
        }
   }

    class ExecuteRectangle
    {
        static void Main(string[] args)
        {
            Tabletop myTabletop = new Tabletop(4.5, 8.5);
            myTabletop.Display();
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/inheritance
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/inheritance

## Полиморфизм / Изменение членов

Слово "полиморфизм" означает "имеющий много форм". В C# полиморфизм означает, что один и тот же метод может иметь несколько различных реализаций. Обычно полиморфизм возникает, когда есть иерархия классов, связанных отношением наследования от общего базового класса.

Полиморфизм означает, что вызов метода будет вызывать выполнение другой реализации в зависимости от типа объекта, вызывающего метод.

```csharp
using System;

namespace SamplePolymorphism
{
    class Program
    {
        class Shape
        {
            // The "virtual" keyword is used below to allow the method to be overridden in a derived class.
            public virtual void Draw()
            {
                Console.WriteLine("The act of drawing!");
            }
        }

        class Circle : Shape
        {
            // The "override" modifier is required for modifying the virtual implementation of the inherited method.
            public override void Draw()
            {
                Console.WriteLine("Draw a circle");
            }
        }

        class Rectangle : Shape
        {
            public override void Draw()
            {
                Console.WriteLine("Draw a rectangle");
            }
        }

        static void Main(string[] args)
        {
            Shape myCircle = new Circle();
            myCircle.Draw();

            Shape myRectangle = new Rectangle();
            myRectangle.Draw();
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/polymorphism

## Свойство Static

Используйте модификатор "static", чтобы объявить статический член, который принадлежит самому типу, а не конкретному объекту.

Модификатор "static" можно использовать для объявления статических классов. В классах, интерфейсах и структурах вы можете добавить модификатор "static" к полям, методам, свойствам, операторам, событиям и конструкторам.

**Примечание 1:** Модификатор "static" нельзя использовать с индексаторами или финализаторами.

**Примечание 2:** Целый класс можно объявить статическим.

**Примечание 3:** Статический класс может содержать только статические члены.

**Примечание 4:** Вы не можете создать экземпляр объекта статического класса, так как в программе может существовать только одна копия статического класса.

Начиная с C# 8.0, вы можете добавить модификатор "static" к локальной функции. Статическая локальная функция не может захватывать локальные переменные или состояние экземпляра.

Начиная с C# 9.0, вы можете добавить модификатор "static" к лямбда-выражению или анонимному методу. Статический лямбда или анонимный метод не может захватывать локальные переменные или состояние экземпляра.

```csharp
using System;

namespace StaticDemonstration
{
    static class User
    {
        // Static Variables
        public static string name;
        public static string location;
        public static int age;

        // Static Method
        public static void Details()
        {
            Console.WriteLine($"The user details are: {name} - {age} - {location}");
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            // Assigning values to public static variables:
            User.name = "Kayako Yamada";
            User.location = "Japan";
            User.age = 30;

            // Accessing public static variables:
            Console.WriteLine($"Name: {User.name}");
            Console.WriteLine($"Location: {User.location}");
            Console.WriteLine($"Age: {User.age}");

            // Calling a public static method:
            User.Details();
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/static
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members

## Свойства

Свойства в C# предоставляют возможность защитить поле, читая и записывая в него через специальные методы, называемые **доступами**. Они обычно объявляются как `public` с тем же типом данных, что и поле, которое они защищают, за которым следует имя свойства, а затем блок кода, который определяет методы `get` и `set` доступа.

Свойства позволяют разработчикам изменять внутреннюю реализацию свойства без нарушения работы любых программ, использующих его.

**Примечание 1:** Хорошей практикой является инкапсуляция членов класса и предоставление доступа к ним только через публичные методы. Свойства предоставляют гибкий механизм для чтения, записи или вычисления значения приватного поля.

**Примечание 2:** Рекомендуется, чтобы имя свойства было идентично имени приватного поля с использованием заглавной буквы.

**Примечание 3:** Любой доступ к свойству может быть пропущен по усмотрению в зависимости от цели и проектирования программы.

**Примечание 4:** Свойство также может быть приватным, поэтому его можно вызывать только изнутри класса.

```csharp
using System;

namespace PropertiesDemonstration
{
    class Person
    {
        private string name; // Private string that requires a property to access it from outside the class.
        private ushort age; // Private unsigned short that requires a property to access it from outside the class.

        public string Name // Property of type string.
        {
            get { return name; }
            set { name = value; }
            // "value" is a keyword, which represents the value we assign to a property using the set accessor.
        }

        public ushort Age // Property of type string.
        {
            get { return age; }

            set
            {
                if (value >= 18) // Validating the value before assigning it to the private member.
                {
                    age = value;
                }
            }
        }

        public string Title { get; set; }
        // Title is an auto-implemented property (Auto-Properties). It allows you to define the property without declaring the private field name separately. It is created by the property automatically. That allows a short declaration of private members.

        static void Main(string[] args)
        {
            Person teacher = new Person();

            teacher.Name = "James";
            teacher.Title = "Dr.";
            teacher.Age = 38;

            Console.WriteLine($"Welcome: {teacher.Title} {teacher.Name} {teacher.age}");
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/properties
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/properties

## Индексаторы

Индексаторы позволяют экземплярам класса или структуры быть индексированными, как массивы. Индексированное значение можно установить или получить без явного указания типа или члена экземпляра. Индексаторы похожи на свойства, за исключением того, что их доступные методы принимают параметры.

Декларация индексатора в некотором роде напоминает декларацию свойства. Разница в том, что доступные методы индексатора требуют индекса. Как и для свойств, вы используете методы get и set для определения индексатора. Однако, в отличие от свойств, которые возвращают или устанавливают конкретное поле объекта, индексаторы возвращают или устанавливают определенное значение из экземпляра объекта.

**Примечание 1:** Индексаторы определяются с использованием ключевого слова `this`.

**Примечание 2:** Обычно программисты используют индексаторы, когда класс представляет список, коллекцию или массив объектов.

```csharp
using System;

namespace IndexerDemonstration
{
    class Program
    {
        class Clients
        {
            private string[] names = new string[10];

            public string this[int index]
            {
                get
                {
                    return names[index];
                }

                set
                {
                    names[index] = value;
                }
            }
        }

        static void Main(string[] args)
        {
            Clients myClients = new Clients();

            myClients[0] = "Jane";
            myClients[1] = "Oliver";
            myClients[2] = "Amy";

            Console.WriteLine(myClients[1]); // Oliver
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/indexers/

## Абстракция

#### Абстрактные классы и методы

Полиморфизм используется, когда у вас есть различные производные классы с одним и тем же методом, который имеет разные реализации в каждом классе. Это поведение достигается с помощью виртуальных методов, которые переопределяются в производных классах.

В некоторых ситуациях нет необходимости, чтобы виртуальный метод имел отдельное определение в базовом классе. Эти методы определяются с использованием ключевого слова `abstract`. Это указывает, что производные классы должны определить этот метод самостоятельно.

**Модификатор abstract** указывает, что модифицируемый объект имеет пропущенную или неполную реализацию. Модификатор abstract может использоваться с классами, методами, свойствами, индексаторами и событиями.

Используйте модификатор abstract в объявлении класса, чтобы указать, что класс предназначен только в качестве базового класса для других классов, а не для создания экземпляров самостоятельно. Члены, помеченные как abstract, должны быть реализованы не-абстрактными классами, производными от абстрактного класса.

**Примечание:** Объекты не могут быть созданы из класса, содержащего абстрактный метод, поскольку класс сам по себе является абстрактным.

```csharp
using System;

abstract class BaseClass // Abstract Class
{
    // Protected Integers
    protected int _x = 0;
    protected int _y = 0;

    // Public Abstract Method
    public abstract void IncrementValues();

    // Abstract Properties
    public abstract int X { get; }
    public abstract int Y { get; }
}

class DerivedClass : BaseClass
{
    public override void IncrementValues()
    {
        _x++;
        _y++;
    }

    public override int X   // Overriding Property
    {
        get
        {
            return _x;
        }
    }

    public override int Y   // Overriding Property
    {
        get
        {
            return _y;
        }
    }

    static void Main(string[] args)
    {
        var myObject = new DerivedClass();
        myObject.IncrementValues(); // Incrementing X & Y by one
        Console.WriteLine($"x = {myObject.X}, y = {myObject.Y}"); // x = 1, y = 1
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/abstract

## Интерфейсы

Интерфейс — это полностью абстрактный класс, содержащий только абстрактные члены. Он объявляется с использованием ключевого слова `interface`.

Когда класс реализует интерфейс, он также должен реализовать, или определить, все его методы.

Термин "**реализация интерфейса**" используется (в отличие от термина "наследование от") для описания процесса создания класса на основе интерфейса. Интерфейс просто описывает, что должен делать класс. Класс, реализующий интерфейс, должен определить, как это поведение будет выполнено.

Класс может наследовать только от одного базового класса, но может реализовывать **несколько интерфейсов**. Таким образом, с помощью интерфейсов вы можете включить поведение из нескольких источников в класс. Чтобы реализовать несколько интерфейсов, используйте список, разделенный запятыми, при создании класса.

**Примечание 1:** Все члены интерфейса по умолчанию являются абстрактными, поэтому нет необходимости использовать ключевое слово `abstract`.

**Примечание 2:** Все члены интерфейса всегда являются публичными, и к ним нельзя применять модификаторы доступа.

**Примечание 3:** Обычно используется буква `I` в качестве первой буквы имени интерфейса.

**Примечание 4:** Интерфейсы не могут содержать поля (переменные).

```csharp
using System;

namespace InterfacesDemonstration
{
    interface IInfo
    {
        void DoInform();
    }

    interface IVersion
    {
        void GetVersion();
    }

    interface ILog : IInfo, IVersion
    {
        void DoLog();
    }

    class DBConnect : ILog
    {
        public void DoInform()
        {
            Console.WriteLine("This is the DBConnect class");
        }

        public void GetVersion()
        {
            Console.WriteLine("Version 1.0.0");
        }

        public void DoLog()
        {
            Console.WriteLine("Logging");
        }

        public void Connect()
        {
            Console.WriteLine("Connecting to the database");
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            var db = new DBConnect();

            db.DoInform();
            db.GetVersion();
            db.DoLog();
            db.Connect();
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/interfaces/
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/interface

### Namespaces

**Namespaces** предоставляют способ группировки связанных элементов верхнего уровня в иерархию. Они также используются для предотвращения конфликтов имен. Элемент верхнего уровня, такой как класс, который не входит в пространство имен, считается принадлежащим к **стандартному пространству имен**. Его можно переместить в другое пространство имен, заключив его в блок пространства имен. Вы можете использовать пространство имен для организации кодовых элементов. Вы можете определить свои собственные пространства имен и использовать их в своей программе.

**Свойства пространств имен:**

- Они организуют большие проекты по программированию.
- Они ограничены использованием оператора ``.``.
- Ключевое слово `using` указывает, что программа использует определенное пространство имен.
- Глобальное пространство имен является корневым пространством имен: `1global::System` всегда будет ссылаться на пространство имен **.NET** System.

**Примечание 1:** Соглашения о наименовании пространств имен такие же, как и для классов, с каждой словоформой, начинающейся с заглавной буквы.

**Примечание 2:** **.NET Framework** использует пространства имен для организации своих классов.

```csharp
namespace NamespaceDemonstration
{
    class Program
    {
        static void Main(string[] args)
        {
            System.Console.WriteLine("Hello World!");
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/namespaces/

## Перегрузка операторов

**Перегрузка операторов** позволяет операторам быть **переопределенными** и использоваться там, где один или оба операнта принадлежат определенному классу. Когда это делается правильно, это может упростить код и сделать пользовательские типы такими же простыми в использовании, как и простые типы.

Перегруженные операторы — это методы с особыми именами, которые следуют за ключевым словом `operator` и символом оператора, который определяется. Подобно любому другому методу, перегруженный оператор имеет тип возвращаемого значения и список параметров.

```csharp
using System;

namespace OperatorOverloadDemonstration
{
    class Program
    {
        class Box
        {
            public int Height { get; set; }
            public int Width { get; set; }

            public Box(int h, int w) // The constructor of the class.
            {
                Height = h;
                Width = w;
            }

            public static Box operator+(Box a, Box b) // Overloading the + operator
            {
                int h = a.Height + b.Height;
                int w = a.Width + b.Width;

                Box result = new Box(h, w);
                return result;
            }
        }
        static void Main(string[] args)
        {
            Box b1 = new Box(14, 3);
            Box b2 = new Box(5, 7);
            Box b3 = b1 + b2;

            Console.WriteLine(b3.Height);
            Console.WriteLine(b3.Width);
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/operator-overloading

---

## Делегаты

Делегат — это тип, используемый для ссылки на метод. Это позволяет методам присваиваться переменным и передаваться в качестве аргументов. Объявление делегата определяет сигнатуру метода, на который могут ссылаться объекты типа делегата. Делегиты именуются в соответствии с общепринятым соглашением, где каждое слово начинается с заглавной буквы, а `Delegate` находится в конце имени.

Иными словами, делегит — это тип данных ссылок, который определяет сигнатуру метода. Вы можете определять переменные делегитов, как и другие типы данных, которые могут ссылаться на любой метод с той же сигнатурой, что и делегит.

**Примечание 1:** При необходимости вы также можете передавать делегиты в качестве параметров.

**Примечание 2:** В C# также можно определить обобщенные делегиты.

**Примечание 3:** В .NET [```Func```](https://docs.microsoft.com/en-us/dotnet/api/system.func-1) и [```Action```](https://docs.microsoft.com/en-us/dotnet/api/system.action) являются встроенными обобщенными делегатами, которые следует использовать для большинства распространенных делегатов, а не создавать новые пользовательские.

Работа с делегатами включает три шага:

1. Объявить делегат
2. Установить целевой метод
3. Вызвать делегат

**Синтаксис делегатов:**

```
[access modifier] delegate [return type] [delegate name]([parameters])
```

**Демонстрация делегата:**

```csharp
namespace DelegatesDemonstration
{
    public delegate int MyDelegate(int x, int y);

    public class Program
    {
        static int Sum(int x, int y)
        {
            return x + y;
        }

        public static void Main(string[] args)
        {
            // Simplified Syntax which was introduced in C# 2.0
            MyDelegate delegateObject = Sum;

            // Execute the delegate object using the Invoke keyword
            int result = delegateObject(12, 15);

            /* Alternative Syntax:

            MyDelegate delegateObject = new MyDelegate(Sum);
            int result = delegateObject.Invoke(12, 15);

            */

            System.Console.WriteLine(result);
        }
    }
}
```

**Демонстрация делегата многоадресной рассылки:**

```csharp
using System;

public delegate void MyDelegate(string msg);

public class ClassA
{
    public static void MethodA(string message)
    {
        Console.WriteLine("Called ClassA.MethodA() with parameter: " + message);
    }
}

public class ClassB
{
    public static void MethodB(string message)
    {
        Console.WriteLine("Called ClassB.MethodB() with parameter: " + message);
    }
}

public class Program
{
    public static void Main(string[] args)
    {
        MyDelegate del1 = ClassA.MethodA;
        MyDelegate del2 = ClassB.MethodB;

        MyDelegate del = del1 + del2;
        Console.WriteLine("After del1 + del2");
        del("Hello World");

        // Lambda expressions achieve the same goal as anonymous methods but with a concise syntax.
        MyDelegate del3 = (string msg) => Console.WriteLine("Called lambda expression: " + msg);
        del += del3;
        Console.WriteLine("After del1 + del2 + del3");
        del("Hello World");

        del = del - del2;
        Console.WriteLine("After del - del2");
        del("Hello World");

        del -= del1;
        Console.WriteLine("After del1 - del1");
        del("Hello World");
    }
}
```

**Общая демонстрация делегата:**

```csharp
using System;

public delegate T GenericAdd<T>(T param1, T param2);

public class Program
{
    public static int Sum(int val1, int val2)
    {
        return val1 + val2;
    }

    public static string Concat(string str1, string str2)
    {
        return str1 + str2;
    }

    public static void Main(string[] args)
    {
        GenericAdd<int> mySum = Sum;
        Console.WriteLine(mySum(10, 20));

        GenericAdd<string> myConcat = Concat;
        Console.WriteLine(myConcat("Hello ", "World!"));
    }
}
```

## Встроенные делегаты

C# предоставляет некоторые встроенные делегаты, которые полезны для общих целей. Они предоставляют сокращенную запись, которая практически исключает необходимость объявления типов делегатов.

**Примеры:**

- **Action**: используется с методами, которые не возвращают значение и не имеют списка параметров.
- **Action<>**: используется с методами, которые, по крайней мере, имеют один аргумент и не возвращают значение.
- **Func<>**: используется с методами, которые возвращают значение и могут иметь список параметров.
- **Predicate<>**: представляет метод, который принимает один входной параметр и возвращает булево значение на основе некоторых критериев.

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/delegates/
https://docs.microsoft.com/en-us/dotnet/api/system.delegate

## Анонимные методы

Анонимные методы были введены в C# 2.0. Они могут быть присвоены объектам делегатов. Анонимный метод определяется с помощью ключевого слова `delegate`, за которым следует список параметров и тело метода. Это может упростить создание экземпляров делегатов, поскольку отдельный метод не нужно определять для создания экземпляра делегата.

```csharp
delegate void MyDelegate(string str);

public class Program
{
    public static void Main(string[] args)
    {
        MyDelegate delegateObj = delegate(string s)
        {
            System.Console.WriteLine(s);
        };

        delegateObj.Invoke("Hello World!");

        /* Alternative Syntax:
        delegateObj("Hello World!");
        */
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/statements-expressions-operators/anonymous-functions

## Выражения лямбда

Выражения лямбда были введены в C# 3.0. Они достигают той же цели, что и анонимные методы, но с более компактным синтаксисом. Выражение лямбда записывается в виде списка параметров, за которым следует оператор лямбда (=>) и выражение.

```csharp
namespace LambdaDemonstration
{
    delegate int MyDelegate(int i);

    public class Program
    {
        public static void Main(string[] args)
        {
            // Anonymous Method
            MyDelegate delegateObj1 = delegate(int x) { return x * x; };

            // Lambda expression
            MyDelegate delegateObj2 = (int x) => x * x;

            System.Console.WriteLine(delegateObj1(5)); // 25
            System.Console.WriteLine(delegateObj2(5)); // 25
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/lambda-expressions

---

## События

События позволяют классу или объекту уведомлять другие классы или объекты о возникновении чего-либо интересного. Класс, который отправляет (или вызывает) событие, называется **распространителем**, а классы, которые получают (или обрабатывают) событие, называются **подписчиками**.

Рассматривайте событие как **инкапсулированный делегат**; Он зависит от делегата. Делегат определяет сигнатуру метода обработчика событий класса-подписчика. Он также избегает перезаписи ссылки на метод путем ограничения использования оператора присваивания `=``.

**Объявление событий:**

- **Шаг 1:** Объявить делегат.
- **Шаг 2:** Объявить переменную делегата с ключевым словом `event`.

**Простая демонстрация:**

```csharp
namespace EventDemonstration
{
    public delegate string MyDelegate(string str); // Declare the delegate.

    public class EventClass
    {
        event MyDelegate MyEvent; // Declare a variable of the delegate with event keyword.

        public EventClass() // The constructor
        {
            // Register with an event
            MyEvent += WelcomeUser;

            /* Alternative Syntax:
            this.MyEvent += new MyDelegate(this.WelcomeUser);
            */
        }

        public string WelcomeUser(string username)
        {
            return "Welcome " + username;
        }

        public static void Main(string[] args)
        {
            EventClass myObject = new EventClass();
            System.Console.Write(myObject.MyEvent("Amy"));
        }
    }
}
```

## Примечания:

- Событие является оберткой для делегата. Оно зависит от делегата.
- Используйте ключевое слово "event" с типом делегата переменной для объявления события.
- Используйте встроенный делегат `EventHandler` или `EventHandler<TEventArgs>` для общих событий.
- Распространительный класс вызывает событие, а класс-подписчик регистрируется на событие и предоставляет метод обработчика событий.
- Название метода, который вызывает событие, начинается с "**On**" с именем события.
- Подпись метода обработчика событий должна соответствовать подписи делегата.
- Зарегистрируйтесь на событие, используя оператор `+=``.
- Отмените регистрацию на событие, используя оператор `-=``.
- Передайте данные события, используя `EventHandler<TEventArgs>`.
- Создайте класс пользовательских данных события, наследовавшись от `EventArgs`.
- События могут быть объявлены как `static`, `virtual`, `sealed` и `abstract`.
- Интерфейс может включать событие в качестве члена.
- Обработчики событий вызываются **синхронно**, если есть несколько подписчиков.

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/events/

---

## Обобщенные типы

Обобщенные типы вводят концепцию параметрических типов в .NET, что позволяет проектировать классы и методы, которые откладывают спецификацию одного или нескольких типов до момента объявления и создания экземпляров класса клиентом.

```csharp
using System;
using System.Collections.Generic;

namespace Example
{
    class Program
    {
        class Stack<T>
        {
            int index = 0;
            T[] innerArray = new T[100];

            public void Push(T item)
            {
                innerArray[index++] = item;
            }

            public T Pop()
            {
                return innerArray[--index];
            }

            public T Get(int k) { return innerArray[k]; }
        }

        static void Main(string[] args)
        {
          // Defining a stack of integers
            Stack<int> intStack = new Stack<int>();
            intStack.Push(1);
            intStack.Push(2);
            intStack.Push(3);
            Console.WriteLine(intStack.Get(1)); // Output => 2

            // Defining a stack of strings
            Stack<string> strStack = new Stack<string>();
          strStack.Push("Jane");
            strStack.Push("James");
            strStack.Push("John");
            Console.WriteLine(strStack.Get(0)); // Output => Jane
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/generics/

---

## Обобщенные коллекции

Коллекция используется для группировки связанных объектов. В отличие от массива, она динамическая и также может группировать объекты. Коллекция может расти и уменьшаться, чтобы вместить любое количество объектов. Классы коллекций организованы в пространства имен и содержат встроенные методы для обработки элементов в коллекции.

Коллекция организует связанные данные в компьютере таким образом, чтобы их можно было использовать эффективно. Разные виды коллекций подходят для разных видов приложений, и некоторые из них специализированы для конкретных задач.

Коллекция обычно включает методы для добавления, удаления и подсчета объектов. Для перебора элементов коллекции используются оператор `for...in` и оператор `foreach`. Поскольку коллекция является классом, вам сначала необходимо объявить экземпляр класса, прежде чем добавлять элементы в эту коллекцию.

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/standard/generics/collections

## Список

Список похож на массив, но элементы в списке можно добавлять и удалять динамически. Обобщенный класс коллекции C# `List<T>` требует, чтобы все элементы были одного типа `T`.

```csharp
using System;
using System.Collections.Generic;

namespace SampleList
{
    class Program
    {
        static void Main(string[] args)
        {
            List<int> liNumbers = new List<int>();

            liNumbers.Add(59);
            liNumbers.Add(72);
            liNumbers.Add(95);
            liNumbers.Add(5);
            liNumbers.Add(9);
            liNumbers.RemoveAt(1); // remove 72

            Console.Write("\nList: ");
            for (int x = 0; x < liNumbers.Count; x++)
            {
                Console.Write($"{liNumbers[x]} "); // 59  95  5  9
            }

            liNumbers.Sort();

            Console.Write("\nSorted: ");
            for (int x = 0; x < liNumbers.Count; x++)
            {
                Console.Write($"{liNumbers[x]} "); // 5  9  59  95
            }
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1

## Отсортированный список

Отсортированный список - это коллекция пар ключ/значение, которые упорядочены по ключу. Ключ может использоваться для доступа к соответствующему значению в отсортированном списке.

Обобщенный класс коллекции C# `SortedList<K, V>` требует, чтобы все элементы в коллекции имели одинаковые типы ключей `K` и значений `V`. Дублирующиеся ключи не допускаются, что гарантирует уникальность каждой пары ключ/значение.

```csharp
using System;
using System.Collections.Generic;

namespace SampleSortedList
{
    class Program
    {
        static void Main(string[] args)
        {
            SortedList<string, int> slMarks = new SortedList<string, int>();

            slMarks.Add("Jane", 70);
            slMarks.Add("Kate", 30);
            slMarks.Add("James", 90);
            slMarks.Remove("Kate");

            Console.WriteLine("Sorted List: ");
            foreach (string s in slMarks.Keys)
            {
                Console.WriteLine($"{s} : {slMarks[s]}");  // Jane: 70  James: 90
            }

            Console.WriteLine($"Count: {slMarks.Count}");  // 2
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedlist-2

## Битовый массив

Битовый массив - это коллекция битов. Значение бита может быть либо 0 (выключено/ложь), либо 1 (включено/истина). Битовые массивы компактно хранят биты. Чаще всего они используются для представления простой группы флагов булевого типа или упорядоченной последовательности булевых значений.

```csharp
using System;
using System.Collections;
using System.Collections.Generic;

namespace SampleBitArray
 {
    class Program
    {
        // Printing BitArray
        public static void PrintBarr(string name, BitArray ba)
        {
            Console.Write(name + " : ");

            for (int x = 0; x < ba.Length; x++)
            {
                Console.Write(ba.Get(x) + " ");
            }

            Console.WriteLine();
        }

        public static void Main(string[] args)
        {
            BitArray ba1 = new BitArray(4);
            BitArray ba2 = new BitArray(4);

            ba1.SetAll(true);
            ba2.SetAll(false);

            ba1.Set(2, false);
            ba2.Set(3, true);

            PrintBarr("ba1", ba1);
            PrintBarr("ba2", ba2);

            Console.WriteLine();
            PrintBarr("ba1 AND ba2", ba1.And(ba2));
            PrintBarr("NOT ba2", ba2.Not());
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray

## Стек

Стек - это коллекция элементов "последний вошел, первый вышел" (LIFO), в которой последний элемент, который входит в стек, будет первым элементом, который выйдет из него.

Вставка элемента в стек называется "толкать". Удаление элемента из стека называется "выталкивать". Вставку и удаление можно выполнять только на вершине стека.

Стеки могут использоваться для создания функциональности отмены/восстановления, разбора выражений (преобразование из infix в postfix/prefix), а также для гораздо большего.

Обобщенный класс коллекции C# `Stack<T>` требует, чтобы все элементы в стеке были одного типа `T`.

```csharp
using System;
using System.Collections.Generic;

namespace SampleStack
{
    class Program
    {
        static void Main(string[] args)
        {
            Stack<int> s = new Stack<int>();

            s.Push(59);
            s.Push(72);
            s.Push(65);

            Console.Write("Stack: ");
            foreach (int i in s)
            {
                Console.Write(i + " ");  // 65  72  59
            }

            Console.WriteLine($"\nCount: {s.Count}");  // 3
            Console.WriteLine($"Top: {s.Peek()}");  // 65
            Console.WriteLine($"Pop: {s.Pop()}");  // 65

            Console.Write("\nStack: ");
            foreach (int i in s)
            {
                Console.Write(i + " "); // 72 59
            }
            Console.WriteLine($"\nCount: {s.Count}"); // Count: 2
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.stack-1

## Очередь

Очередь - это коллекция элементов "первый вошел, первый вышел" (FIFO), в которой первый элемент, который входит в очередь, будет первым элементом, который выйдет из нее.

Вставка элемента в очередь называется "записать". Удаление элемента из очереди называется "удалить". Запись и удаление выполняются только на вершине очереди.

Очереди используются всякий раз, когда нам необходимо управлять объектами в порядке их появления, начиная с первого.

Обобщенный класс коллекции C# `Queue<T>` требует, чтобы все элементы в очереди были одного типа `T`.

```csharp
using System;
using System.Collections.Generic;

namespace SampleQueue
{
    class Program
    {
        static void Main(string[] args)
        {
            Queue<int> q = new Queue<int>();

            q.Enqueue(5);
            q.Enqueue(10);
            q.Enqueue(15);

            Console.Write("Queue: ");
            foreach (int i in q)
            {
                Console.Write(i + " "); // 5 10 15
            }

            Console.WriteLine($"\nCount: {q.Count} \n");  // Count: 3
            Console.WriteLine($"Dequeue: {q.Dequeue()} \n"); // Dequeue: 5

            Console.Write("Queue: ");
            foreach (int i in q)
            {
                Console.Write(i + " "); // Queue: 10 15
            }
            Console.WriteLine($"\nCount: {q.Count}"); // Count: 2
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1

## Словарь

Словарь - это коллекция уникальных пар ключ/значение, где ключ используется для доступа к соответствующему значению. Словари используются в индексировании баз данных, реализации кэша и т.д.

Обобщенный класс коллекции C# `Dictionary<K, V>` требует, чтобы все элементы в словаре имели одинаковые типы ключей `K` и значений `V`. Дублирующиеся ключи не допускаются, что гарантирует уникальность каждой пары ключ/значение.

```csharp
using System;
using System.Collections.Generic;

namespace SampleDictionary
{
    class Program
    {
        static void Main(string[] args)
        {
            Dictionary<string, int> d = new Dictionary<string, int>();

            d.Add("Uno", 1);
            d.Add("Dos", 2);
            d.Add("Tres", 3);

            d.Remove("Tres"); // Remove key-value pair Tres, 3

            Console.WriteLine("Dictionary: ");
            foreach (string s in d.Keys)
            {
                Console.Write($"{s} : {d[s]} "); // Uno: 1 Dos: 2
            }
            Console.WriteLine($"\nCount: {d.Count}"); // Count: 2
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.dictionary-2

## Хэш-набор

Хэш-набор - это множество уникальных значений, в котором дубликаты не допускаются.

В C# есть класс `HashSet<T>`, определенный в пространстве имен `System.Collections.Generic`, где `T` - это параметр типа. Все элементы в `HashSet<T>` должны быть одного и того же типа `T`.

Хэш-набор отличаются от других коллекций тем, что они представляют собой просто множество значений. У них нет индексных позиций, и элементы не могут быть упорядочены.

Класс `HashSet<T>` предоставляет высокопроизводительные операции множества. Хэш-наборы позволяют быстро выполнять поиск, добавление и удаление элементов, и могут использоваться для реализации динамических множеств элементов или таблиц поиска, которые позволяют находить элемент по его ключу.

```csharp
using System;
using System.Collections.Generic;

namespace SampleHashSet
{
    class Program
    {
        static void Main(string[] args)
        {
            HashSet<int> hs = new HashSet<int>();

            hs.Add(5);
            hs.Add(10);
            hs.Add(15);
            hs.Add(20);

            Console.Write("HashSet: ");
            foreach (int i in hs)
            {
                Console.Write(i + " ");
            }
            Console.WriteLine($"\nCount: {hs.Count}"); // Count: 4

            HashSet<int> hs2 = new HashSet<int>();
            hs2.Add(15);
            hs2.Add(20);
            Console.WriteLine("{15, 20} is a subset of {5, 10, 15, 20} : " + hs2.IsSubsetOf(hs));
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1

---

## Константы

### Ключевое слово "const"

Переменную в C# можно сделать компиляционной константой, добавив ключевое слово "const" перед типом данных. Этот модификатор означает, что переменная не может быть изменена и ее значение должно быть присвоено одновременно с ее объявлением. Любые попытки присвоить переменной новое значение приведут к ошибке компиляции.

```csharp
static void Main(string[] args)
{
    const double Pi = 3.14159265358979323846; // compile-time constant
}
```

## Примечание:
Константные поля не могут иметь модификатор `static`. Они по умолчанию являются статическими и к ним обращаются так же, как и к статическим полям.

### Ключевое слово "readonly"

Еще одно ключевое слово, аналогичное `const`, - это `readonly`. Оно создает константу времени выполнения. Этот модификатор может применяться к полям, и, как и `const`, он делает поле неизменяемым.

**Примечание 1:** В отличие от `const`, `readonly` может применяться к любому типу данных.

**Примечание 2:** `readonly` поле может быть инициализировано только один раз, либо при его объявлении, либо в конструкторе.

**Примечание 3:** Поскольку `readonly` поле инициализируется во время выполнения, ему может быть присвоено динамическое значение, которое неизвестно до момента выполнения.

**Примечание 4:** Вы также можете пометить возвращаемое значение метода как `readonly`, когда возвращается значение типа ссылка на значение, используя модификатор `ref`. Это предотвратит изменение возвращаемого значения вызывающим методом, при условии, что возвращаемое значение также было присвоено как `readonly` ссылка, а не просто копия.

```csharp
class MyClass
{
    readonly static int i;

    static ref readonly int GetValue()
    {
        return ref i;
    }

    static void Main(string[] args)
    {
        ref readonly int myValue = ref GetValue();
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/constants
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/const

---

## Асинхронные методы

Асинхронный метод — это метод, который может **вернуть** до того, как он закончит выполнение. Любой метод, который выполняет потенциально длительную задачу, такую как доступ к веб-ресурсу или чтение файла, может быть сделан асинхронным для улучшения отзывчивости программы.

Ключевые слова `async` и `await` позволяют писать асинхронные методы с простой структурой, которая похожа на синхронные (обычные) методы. Ключевое слово `async` указывает, что метод асинхронный и может содержать одно или несколько выражений `await`. Выражение `await` состоит из ключевого слова `await`, за которым следует вызываемый асинхронный метод.

```csharp
class MyApp
{
    async void MyAsync()
    {
        System.Console.Write("A");
        await System.Threading.Tasks.Task.Delay(2000);
        System.Console.Write("C");
    }
}

static void Main(string[] args)
{
    new MyApp().MyAsync();
    System.Console.Write("B");

    // Outputs: ABC
    System.Console.ReadKey(); // Prevents the console program from exiting before the async method has finished.
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/async
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/async/

---

## Работа с файлами

Пространство имен `System.IO` содержит различные классы, которые используются для выполнения множества операций с файлами, таких как создание и удаление файлов, чтение из или запись в файл, закрытие файла и т.д. Класс `File` является одним из них.

Популярные методы класса `File`:

- **AppendAllText()** : Добавляет текст в конец файла.
- **Create()**        : Создает файл в указанном месте.
- **Delete()**        : Удаляет указанный файл.
- **Exists()**        : Определяет, существует ли указанный файл.
- **Copy()**          : Копирует файл в новое место.
- **Move()**          : Перемещает указанный файл в новое место.

```csharp
using System;
using System.IO;

namespace Example
{
    class Program
    {
        static void Main(string[] args)
        {
            string str = "Working with files in C#";
            File.WriteAllText("example.txt", str);

            string txt = File.ReadAllText("example.txt");
            Console.WriteLine(txt);
        }
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/api/system.io.file

---

## Встроенный язык запросов (LINQ)

Встроенный язык запросов (LINQ) — это название для набора технологий, основанных на интеграции возможностей запросов непосредственно в язык C#. Традиционно запросы против данных выражаются в виде простых строк без проверки типов на этапе компиляции или поддержки IntelliSense.

```csharp
class LINQQueryExpressions
{
    static void Main()
    {
        // Specify the data source.
        int[] scores = new int[] { 97, 92, 81, 60 };

        // Define the query expression.
        IEnumerable<int> scoreQuery =
            from score in scores
            where score > 80
            select score;

        // Execute the query.
        foreach (int i in scoreQuery)
        {
            Console.Write(i + " ");
        }
    }
}
// Output: 97 92 81
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/linq/
https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/working-with-linq
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/

---

## Атрибуты

Атрибут — это декларативный тег, который используется для передачи информации о поведении различных элементов, таких как классы, методы, структуры, перечисления, сборки и т.д., в вашу программу. Вы можете добавлять декларативную информацию в программу, используя атрибут. Декларативный тег представлен квадратными скобками, расположенными над элементом, для которого он используется.

Атрибуты используются для добавления метаданных, таких как инструкции компилятора и другая информация, такая как комментарии, описания, методы и классы, в программу.

В .NET Framework предоставляются две реализации атрибутов:

- Предустановленные атрибуты
- Пользовательские атрибуты

### Предустановленные атрибуты

Предустановленные атрибуты — это атрибуты, которые являются частью библиотеки классов .NET Framework и поддерживаются компилятором C# для определенной цели.

Некоторые популярные предустановленные атрибуты, производные от базового класса `System.Attribute`, включают в себя:

| Атрибут              | Описание                                                       |
| ------------------- | -------------------------------------------------------------- |
| AttributeUsageAttribute | Указывает использование другого атрибута.                      |
| CLSCompliantAttribute  | Показывает, что данный код элемент соответствует спецификации языка C#. |
| ContextStaticAttribute | Указывает, что значение статического поля уникально для указанного контекста. |
| FlagsAttribute       | Указывает, что значение статического поля уникально для указанного контекста. |
| LoaderOptimizationAttribute | Устанавливает политику оптимизации для основного метода по умолчанию. |
| NonSerializedAttribute | Указывает, что поле сериализуемого класса не должно быть сериализовано. |
| ObsoleteAttribute     | Маркирует код элементы, которые устарели и больше не используются. |
| SerializableAttribute  | Указывает, что поле сериализуемого класса может быть сериализовано. |
| ThreadStaticAttribute | Указывает, что значение статического поля уникально для каждого потока. |
| DllImportAttribute     | Указывает, что метод является статической точкой входа в необработанный DLL. |

```csharp
// C# program to demonstrate CLSCompliantAttribute giving a warning message
using System;

// CLSCompliantAttribute applied to entire assembly
[assembly:CLSCompliant(true)]

public class GFG
{
  public uint z;
}

class GFG2
{
  public static void Main(string[] args)
  {
      Console.WriteLine("Demonstrating the CLSCompliantAttribute");
  }
}
```

## Пользовательские атрибуты

Пользовательские атрибуты могут быть созданы в C# для прикрепления декларативной информации к методам, сборкам, свойствам, типам и т.д. любым необходимым способом. Это увеличивает расширяемость .NET Framework.

```csharp
// C# program to demonstrate Custom Attributes
using System;

// AttributeUsage specifies the usage of InformationAttribute
[AttributeUsage(AttributeTargets.Class |
              AttributeTargets.Constructor |
                AttributeTargets.Method, AllowMultiple = true)]

// InformationAttribute is a custom attribute class that is derived from Attribute class
class InformationAttribute : Attribute
{
    public string InformationString{ get; set; }
}

// InformationAttribute is used in student class
[Information(InformationString = "Class")] public class student
{
    private int rollno;
    private string name;

    [Information(InformationString = "Constructor")] public student(int rollno, string name)
    {
        this.rollno = rollno;
        this.name = name;
    }

    [Information(InformationString = "Method")] public void display()
    {
        Console.WriteLine($"Roll Number: {rollno}");
        Console.WriteLine($"Name: {name}");
    }
}

public class GFG
{
    public static void Main(string[] args)
    {
        student s = new student(1001, "Jane Doe");
        s.display();
    }
}
```

**Узнать больше:**
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/attributes/

---

## Ссылки

**Официальная C# документация:**
https://docs.microsoft.com/en-us/dotnet/csharp/

**Официальная ссылка на язык C#:**
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/

**Официальное руководство пользователя Unity:**
https://docs.unity3d.com/Manual/index.html

---

## Создатели шпаргалки

**Подготовлен:**

- [ConstructG.com](https://constructg.com)
- [Labinator.com](https://labinator.com)

**Перевод на русский:** 

- [mesheni](https://github.com/mesheni)

**На основе:**

- В этом руководстве использовано несколько примеров и определений из [Microsoft's .NET documentation](https://docs.microsoft.com/en-us/dotnet/).
