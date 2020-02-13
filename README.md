# <a name='naming'>The official Aviata.kz & Chocotravel.com Kotlin Style Guide</a>

This style guide is created to keep our code at Aviata.kz and Chocotravel.com clean and consistent. 

Our goals are: 
<br><b>- conciseness</b> 
<br><b>- readability</b>
<br><b>- simplicity</b>.

## Inspiration

This style-guide is of a mash-up between the existing Kotlin language style guides. The guidance is drawn from: 

- The [Android Kotlin style guide](https://android.github.io/kotlin-guides/style.html)
- The [Kotlin Coding Conventions](https://kotlinlang.org/docs/reference/coding-conventions.html) 
- The [Ray Wenderlich Kotlin Style Guide](https://github.com/raywenderlich/kotlin-style-guide#nomenclature)
- The [RedMadRobot Style Guide](https://github.com/RedMadRobot/kotlin-style-guide#naming)

# Содержание
1. [Line length](#linelength)
2. [Naming conventions](#naming)
3. [Порядок следования модификаторов](#modifier_order)
4. [Форматирование выражений](#expression_formating)
5. [Функции](#function)
    * 5.1 [Функции с одним выражением](#function_expression)
    * 5.2 [Форматирование вызова функции](#formating_function_calling)
    * 5.3 [Форматирование описания функции](#formating_function_declaration)
    * 5.4 [Вызов переменной функционального типа](#calling_function_variable)
6. [Классы](#classes)
7. [Аннотации](#annotation)
8. [Структура класса](#class_member_order)
9. [Форматирование лямбда-выражений](#lambda_formating)
10. [Использование условных операторов](#condition_operator)
11. [Template header](#template_header)
12. [Файлы](#files)

# <a name='linelength'>Line length</a>
- Maximum line length: 100 characters.

# <a name='naming'>Naming conventions</a>

### Packages

Package names are similar to Java: all __lower-case__, multiple words concatenated together, without hypens or underscores:

### Methods

Written in __lowerCamelCase__. For example `setValue`.

### Fields

Generally, written in __lowerCamelCase__. Fields should **not** be named with Hungarian notation!

Example field names:

```kotlin
class MyClass {
  var id: String,
  val count: Int = 0,
  private var privateField: Int?
}
```

Constant values in the companion object should be written in __uppercase__, with an underscore separating words:

```kotlin
companion object {
  const val THE_ANSWER = 42
}
```
