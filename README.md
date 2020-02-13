# <a>The official Aviata.kz & Chocotravel.com Kotlin Style Guide</a>

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
3. [Spacing](#spacing)
4. [XML Guidance](#xml_guidance)
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

### Classes

Classes should be named in __upperCamelCase__. 

```kotlin
data class MyClass(val id: String, val title: String)
```

If class name and it's parameters cannot fit single, all parameters should be placed on a new line with the closing brace on a separate line as well. 

```kotlin
data class MyClass(
   val id: String,
   val title: String,
   val url: String?
) : Serializable
```

If parent's class name and it's parameters cannot fit single line, then you should stick to the rule above.

```kotlin
data class MyClass(
   val id: String,
   val title: String,
   val url: String?
) : ParentClass(
   val id: String,
   val title: String
)
```

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

### Variables & Parameters

Written in __lowerCamelCase__.

Single character values must be avoided, except for temporary looping variables.

### Getters & Setters

Unlike Java, direct access to fields in Kotlin is preferred. 

# <a name='spacing'>Spacing</a>

Spacing is super important at Aviata.kz and Chocotravel.com. Code needs to be easily readable. 

### Line breaks

Single line break should separate class name and it's fields or methods. Leave line break between methods.

```kotlin
class MyClass {

   var someField: Int?

   fun doSomething() {
      if (someExpression) {
         // ...
      } else {
         // ...
      }
   }
   
   fun anotherMethod() {
      // ...
   }
}
```

### Indentation

Indentation is using tabs (1 tab = 4 spaces).

```kotlin
for (i in 0..9) {
    Log.i(TAG, "index=" + i)
}
```

### Line Wraps

Indentation for line wraps should use 1 tab:

```kotlin
val widget: FlightWidget =
    someLongFunction(where, params, willNotFit, on, aSingle, line)
```

### Brace Style

Only trailing closing-braces should be place on their own line. All others appear the same line as preceding code:

```kotlin
class MyClass {

   fun doSomething() {
      if (someTest) {
         // ...
      } else {
         // ...
      }
   }
}
```

```kotlin
if (someTest) {
   doSomething()
}
```

<b>DONT</b> insert space between class name and the opening brace of the constructor. Insert space between class name and the opening brace of a class.

__BAD:__

```kotlin
class MyClass (...){ 
   // ...
}
```

__GOOD:__

```kotlin
class MyClass(...) {
   // ...
}
```


# <a name='xml_guidance'>XML Guidance</a>

Resource names are equally important as other parts of the code. We name our resources with __lower-case__. Try to name resources regarding their place in the code structure. Also, separate resource according to the screen or feature you are creating them for. Convention should be: <b>screen_widget_resource</b>. For example:

```xml
<!-- Booking List -->
<booking_list_placeholder_title>You don't have any tickets yet</booking_list_placeholder_title>
<booking_list_error_title>Error occurred</booking_list_error_title>

<!-- Booking Details -->
<booking_details_title>Booking details</booking_details_title>
<booking_details_download_pdf>Download PDF</booking_details_download_pdf>
```
