---
title: Referencia de símbolos y operadores
description: Obtenga información sobre los símbolos y operadores utilizados en el lenguaje de programación F#.
ms.date: 02/11/2019
fl_keywords:
- '|>_FS'
ms.openlocfilehash: 4c3af80e8f5a686535b7c09579d29bb3da8591a3
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855404"
---
# <a name="symbol-and-operator-reference"></a>Referencia de símbolos y operadores

En este artículo se incluye una tabla de símbolos y operadores que se utilizan en el lenguaje F#.

> [!NOTE]
> La referencia de API de docs.microsoft.com para F# no está completa. Si encuentra vínculos rotos, en su lugar, consulte la referencia [Documentación de la biblioteca principal de F#](https://fsharp.github.io/fsharp-core-docs/).

## <a name="table-of-symbols-and-operators"></a>Tabla de símbolos y operadores

En la siguiente tabla se describen los símbolos utilizados en el lenguaje F# y se facilita una breve descripción de algunos de los usos del símbolo y los vínculos para más información. Los símbolos están ordenados según el orden del juego de caracteres ASCII.

|Símbolo u operador|Vínculos|Descripción|
|------------------|-----|-----------|
|`!`|[Celdas de referencia](../reference-cells.md)<br /><br />[Expresiones de cálculo](../computation-expressions.md)|<ul><li>Desreferencia una celda de referencia.<br /></li><li>Después de una palabra clave, indica una versión modificada del comportamiento de la misma, controlado por un flujo de trabajo.<br /></li></ul>|
|`!=`||<ul><li>No se utiliza en F#. Utilice `<>` para las operaciones de desigualdad.<br /></li></ul>|
|`"`|[Literales](../literals.md)<br /><br />[Cadenas](../strings.md)|<ul><li>Delimita una cadena de texto.<br /></li></ul>|
|`"""`|[Cadenas](../strings.md)|Delimita una cadena de texto literal. Se diferencia de `@"..."` en que puede indicar un carácter de comilla mediante el uso de comillas simples en la cadena.|
|`#`|[Directivas de compilador](../compiler-directives.md)<br /><br />[Tipos flexibles](../flexible-types.md)|<ul><li>Prefija una directiva de compilador o preprocesador, como `#light`.<br /></li><li>Cuando se usa con un tipo, indica un *tipo flexible*, que hace referencia a un tipo o a cualquiera de sus tipos derivados.<br /></li></ul>|
|`$`||<ul><li>Se utiliza internamente para determinados nombres de variable y función generados por el compilador.<br /></li></ul>|
|`%`|[Operadores aritméticos](arithmetic-operators.md)<br /><br />[Expresiones de código delimitadas](../code-quotations.md)|<ul><li>Calcula el resto entero.<br /></li><li>Se utiliza para ensamblar expresiones en expresiones de código delimitadas con tipo.<br /></li></ul>|
|`%%`|[Expresiones de código delimitadas](../code-quotations.md)|<ul><li>Se utiliza para ensamblar expresiones en expresiones de código delimitadas sin tipo.<br /></li></ul>|
|`%?`|[Operadores que aceptan valores NULL](nullable-operators.md)|<ul><li>Calcula el resto entero, cuando el lado derecho es un tipo que acepta valores NULL.<br /></li></ul>|
|`&`|[Expresiones de coincidencia](../match-expressions.md)|<ul><li>Calcula la dirección de un valor mutable para usarlo al interoperar con otros lenguajes.<br /></li><li>Se utiliza en los patrones AND.<br /></li></ul>|
|`&&`|[Operadores booleanos](boolean-operators.md)|<ul><li>Calcula la operación AND booleana.<br /></li></ul>|
|`&&&`|[Operadores bit a bit](bitwise-operators.md)|<ul><li>Calcula la operación AND bit a bit.<br /></li></ul>|
|`'`|[Literales](../literals.md)<br /><br />[Generalización automática](../generics/automatic-generalization.md)|<ul><li>Delimita un literal de carácter único.<br /></li><li>Indica un parámetro de tipo genérico.<br /></li></ul>|
|<code>&#96;&#96;...&#96;&#96;</code>||<ul><li>Delimita un identificador que de otro modo no sería un identificador válido, como una palabra clave de lenguaje.<br /></li></ul>|
|`( )`|[Unit (Tipo)](../unit-type.md)|<ul><li>Representa el valor único del tipo de unidad.<br /></li></ul>|
|`(...)`|[Tuplas](../tuples.md)<br /><br />[Sobrecarga de operadores](../operator-overloading.md)|<ul><li>Indica el orden en que se evalúan las expresiones.<br /></li><li>Delimita una tupla.<br /></li><li>Se utiliza en las definiciones de operador.<br /></li></ul>|
|`(*...*)`||<ul><li>Delimita un comentario que podría abarcar varias líneas.<br /></li></ul>|
|<code>(&#124;...&#124;)</code>|[Patrones activos](../active-patterns.md)|<ul><li>Delimita un modelo activo. También se denominan *delimitadores de modelo activo*.<br /></li></ul>|
|`*`|[Operadores aritméticos](arithmetic-operators.md)<br /><br />[Tuplas](../tuples.md)<br /><br />[Unidades de medida](../units-of-measure.md)|<ul><li>Cuando se utiliza como un operador binario, multiplica los lados izquierdo y derecho.<br /></li><li>En los tipos, indica el emparejamiento en una tupla.<br /></li><li>Se utiliza en unidades de medida de tipos.<br /></li></ul>|
|`*?`|[Operadores que aceptan valores NULL](nullable-operators.md)|<ul><li>Multiplica los lados izquierdo y derecho, si el lado derecho es un tipo que acepta valores NULL.<br /></li></ul>|
|`**`|[Operadores aritméticos](arithmetic-operators.md)|<ul><li>Calcula la operación de exponenciación (`x ** y` significa `x` elevado a la potencia de `y`).<br /></li></ul>|
|`+`|[Operadores aritméticos](arithmetic-operators.md)|<ul><li>Si se utiliza como un operador binario, suma los lados izquierdo y derecho.<br /></li><li>Cuando se utiliza como un operador unario, indica una cantidad positiva. (Formalmente, genera el mismo valor sin modificar el signo).<br /></li></ul>|
|`+?`|[Operadores que aceptan valores NULL](nullable-operators.md)|<ul><li>Suma los lados izquierdo y derecho, si el lado derecho es un tipo que acepta valores NULL.<br /></li></ul>|
|`,`|[Tuplas](../tuples.md)|<ul><li>Separa los elementos de una tupla o los parámetros de tipo.<br /></li></ul>|
|`-`|[Operadores aritméticos](arithmetic-operators.md)|<ul><li>Si se utiliza como un operador binario, resta el lado derecho del lado izquierdo.<br /></li><li>Si se utiliza como un operador unario, realiza una operación de negación.<br /></li></ul>|
|`-?`|[Operadores que aceptan valores NULL](nullable-operators.md)|<ul><li>Resta el lado derecho del lado izquierdo, si el lado derecho es un tipo que acepta valores NULL.<br /></li></ul>|
|`->`|[Funciones](../functions/index.md)<br /><br />[Expresiones de coincidencia](../match-expressions.md)|<ul><li>En tipos de función, delimita los argumentos y valores devueltos.<br /></li><li>Genera una expresión (en expresiones de secuencia); equivalente a la palabra clave `yield`.<br /></li><li>Utilizado en expresiones de coincidencia.<br /></li></ul>|
|`.`|[Miembros](../members/index.md)<br /><br />[Tipos primitivos](../basic-types.md)|<ul><li>Tiene acceso a un miembro y separa los nombres individuales de un nombre completo.<br /></li><li>Especifica un separador decimal en números de punto flotante.<br /></li></ul>|
|`..`|[Bucles: expresión `for...in`](../loops-for-in-expression.md)|<ul><li>Especifica un intervalo.<br /></li></ul>|
|`.. ..`|[Bucles: expresión `for...in`](../loops-for-in-expression.md)|<ul><li>Especifica un intervalo y un incremento.<br /></li></ul>|
|`.[...]`|[Matrices](../arrays.md)|<ul><li>Tiene acceso a un elemento de matriz.<br /></li></ul>|
|`/`|[Operadores aritméticos](arithmetic-operators.md)<br /><br />[Unidades de medida](../units-of-measure.md)|<ul><li>Divide el lado izquierdo (numerador) entre el lado derecho (denominador).<br /></li><li>Se utiliza en unidades de medida de tipos.<br /></li></ul>|
|`/?`|[Operadores que aceptan valores NULL](nullable-operators.md)|<ul><li>Divide el lado izquierdo entre el lado derecho, si el lado derecho es un tipo que acepta valores NULL.<br /></li></ul>|
|`//`||<ul><li>Indica el principio de una sola línea de comentario.<br /></li></ul>|
|`///`|[Documentación de XML](../xml-documentation.md)|<ul><li>Indica un comentario XML.<br /></li></ul>|
|`:`|[Funciones](../functions/index.md)|<ul><li>En una anotación de tipo, separa un parámetro o nombre de miembro de su tipo.<br /></li></ul>|
|`::`|[Listas](../lists.md)<br /><br />[Expresiones de coincidencia](../match-expressions.md)|<ul><li>Crea una lista. El elemento del lado izquierdo antecede a la lista en el lado derecho.<br /></li><li>Se utiliza en la coincidencia de patrones para separar las partes de una lista.<br /></li></ul>|
|`:=`|[Celdas de referencia](../reference-cells.md)|<ul><li>Asigna un valor a una celda de referencia.<br /></li></ul>|
|`:>`|[Conversiones](../casting-and-conversions.md)|<ul><li>Convierte un tipo en otro que está más arriba en la jerarquía.<br /></li></ul>|
|`:?`|[Expresiones de coincidencia](../match-expressions.md)|<ul><li>Devuelve `true` si el valor coincide con el tipo especificado (incluso si se trata de un subtipo); de lo contrario, devuelve `false` (operador de prueba de tipo).<br /></li></ul>|
|`:?>`|[Conversiones](../casting-and-conversions.md)|<ul><li>Convierte un tipo en otro que está por debajo en la jerarquía.<br /></li></ul>|
|`;`|[Sintaxis detallada](../verbose-syntax.md)<br /><br />[Listas](../lists.md)<br /><br />[Registros](../records.md)|<ul><li>Separa expresiones (se usa principalmente en sintaxis detallada).<br /></li><li>Separa elementos de una lista.<br /></li><li>Separa los campos de un registro.<br /></li></ul>|
|`<`|[Operadores aritméticos](arithmetic-operators.md)|<ul><li>Calcula la operación “menor que”.<br /></li></ul>|
|`<?`|[Operadores que aceptan valores NULL](nullable-operators.md)|Calcula la operación “menor que”, si el lado derecho es un tipo que acepta valores NULL.|
|`<<`|[Funciones](../functions/index.md)|<ul><li>Compone dos funciones en orden inverso; la segunda se ejecuta primero (operador de composición hacia atrás).<br /></li></ul>|
|`<<<`|[Operadores bit a bit](bitwise-operators.md)|<ul><li>Desplaza hacia la izquierda los bits de la cantidad del lado izquierdo, y lo hace en el número de bits especificado en el lado derecho.<br /></li></ul>|
|`<-`|[Valores](../values/index.md)|<ul><li>Asigna un valor a una variable.<br /></li></ul>|
|`<...>`|[Generalización automática](../generics/automatic-generalization.md)|<ul><li>Delimita los parámetros de tipo.<br /></li></ul>|
|`<>`|[Operadores aritméticos](arithmetic-operators.md)|<ul><li>Devuelve `true` si el lado izquierdo no es igual que el lado derecho; de lo contrario, devuelve false.<br /></li></ul>|
|`<>?`|[Operadores que aceptan valores NULL](nullable-operators.md)|<ul><li>Calcula la operación “no es igual a” cuando el lado derecho es un tipo que acepta valores NULL.<br /></li></ul>|
|`<=`|[Operadores aritméticos](arithmetic-operators.md)|<ul><li>Devuelve `true` si el lado izquierdo es menor o igual que el lado derecho; de lo contrario, devuelve `false`.<br /></li></ul>|
|`<=?`|[Operadores que aceptan valores NULL](nullable-operators.md)|<ul><li>Calcula la operación “menor o igual que” cuando el lado derecho es un tipo que acepta valores NULL.<br /></li></ul>|
|<code>&lt;&#124;</code>|[Funciones](../functions/index.md)|<ul><li>Pasa el resultado de la expresión de la derecha a la función de la izquierda (operador de canalización hacia atrás).<br /></li></ul>|
|<code>&lt;&#124;&#124;</code>|[Operadores.&#40; &#60;&#124;&#124; &#41;&#60;'T1,'T2,'U&#62; Función](https://msdn.microsoft.com/visualfsharpdocs/conceptual/operators.%5b-%5bhh-%5d%5b%27t1%2c%27t2%2c%27u%5d-function-%5bfsharp%5d)|<ul><li>Pasa la tupla de dos argumentos del lado derecho a la función del lado izquierdo.<br /></li></ul>|
|<code>&lt;&#124;&#124;&#124;</code>|[Operadores.&#40; &#60;&#124;&#124;&#124; &#41;&#60;'T1,'T2,'T3,'U&#62; Función](https://msdn.microsoft.com/visualfsharpdocs/conceptual/operators.%5b-%5bhhh-%5d%5b%27t1%2c%27t2%2c%27t3%2c%27u%5d-function-%5bfsharp%5d)|<ul><li>Pasa la tupla de tres argumentos del lado derecho a la función del lado izquierdo.<br /></li></ul>|
|`<@...@>`|[Expresiones de código delimitadas](../code-quotations.md)|<ul><li>Delimita una expresión de código con tipos.<br /></li></ul>|
|`<@@...@@>`|[Expresiones de código delimitadas](../code-quotations.md)|<ul><li>Delimita una expresión de código sin tipos.<br /></li></ul>|
|`=`|[Operadores aritméticos](arithmetic-operators.md)|<ul><li>Devuelve `true` si el lado izquierdo es igual que el lado derecho; de lo contrario, devuelve `false`.<br /></li></ul>|
|`=?`|[Operadores que aceptan valores NULL](nullable-operators.md)|<ul><li>Calcula la operación “es igual a” cuando el lado derecho es un tipo que acepta valores NULL.<br /></li></ul>|
|`==`||<ul><li>No se utiliza en F#. Utilice `=` para operaciones de igualdad.<br /></li></ul>|
|`>`|[Operadores aritméticos](arithmetic-operators.md)|<ul><li>Devuelve `true` si el lado izquierdo es mayor que el lado derecho; de lo contrario, devuelve `false`.<br /></li></ul>|
|`>?`|[Operadores que aceptan valores NULL](nullable-operators.md)|<ul><li>Calcula la operación "mayor que" cuando el lado derecho es un tipo que acepta valores NULL.<br /></li></ul>|
|`>>`|[Funciones](../functions/index.md)|<ul><li>Compone dos funciones (operador de composición hacia delante).<br /></li></ul>|
|`>>>`|[Operadores bit a bit](bitwise-operators.md)|<ul><li>Desplaza hacia la derecha los bits de la cantidad del lado izquierdo, y lo hace en el número de posiciones especificado en el lado derecho.<br /></li></ul>|
|`>=`|[Operadores aritméticos](arithmetic-operators.md)|<ul><li>Devuelve `true` si el lado derecho es mayor o igual que el lado izquierdo; de lo contrario, devuelve `false`.<br /></li></ul>|
|`>=?`|[Operadores que aceptan valores NULL](nullable-operators.md)|<ul><li>Calcula la operación “mayor o igual que” cuando el lado derecho es un tipo que acepta valores NULL.<br /></li></ul>|
|`?`|[Parámetros y argumentos](../parameters-and-arguments.md)|<ul><li>Especifica un argumento opcional.<br /></li><li>Se usa como operador para método dinámico y llamadas de propiedad. Debe proporcionar su propia implementación.<br /></li></ul>|
|`? ... <- ...`||<ul><li>Se usa como operador para establecer propiedades dinámicas. Debe proporcionar su propia implementación.<br /></li></ul>|
|`?>=`, `?>`, `?<=`, `?<`, `?=`, `?<>`, `?+`, `?-`, `?*`, `?/`|[Operadores que aceptan valores NULL](nullable-operators.md)|<ul><li>Equivalente a los operadores correspondientes sin el sufijo ?; en la izquierda hay un tipo que acepta valores NULL.<br /></li></ul>|
|`>=?`, `>?`, `<=?`, `<?`, `=?`, `<>?`, `+?`, `-?`, `*?`, `/?`|[Operadores que aceptan valores NULL](nullable-operators.md)|<ul><li>Equivalente a los operadores correspondientes sin el sufijo ?; en la derecha hay un tipo que acepta valores NULL.<br /></li></ul>|
|`?>=?`, `?>?`, `?<=?`, `?<?`, `?=?`, `?<>?`, `?+?`, `?-?`, `?*?`, `?/?`|[Operadores que aceptan valores NULL](nullable-operators.md)|<ul><li>Equivalente a los operadores correspondientes sin los signos de interrogación circundantes, donde ambos lados son tipos que aceptan valores NULL.<br /></li></ul>|
|`@`|[Listas](../lists.md)<br /><br />[Cadenas](../strings.md)|<ul><li>Concatena dos listas.<br /></li><li>Cuando se coloca delante de un literal de cadena, indica que la cadena debe interpretarse literalmente, sin interpretación alguna de los caracteres de escape.<br /></li></ul>|
|`[...]`|[Listas](../lists.md)|<ul><li>Delimita los elementos de una lista.<br /></li></ul>|
|<code>[&#124;...&#124;]</code>|[Matrices](../arrays.md)|<ul><li>Delimita los elementos de una matriz.<br /></li></ul>|
|`[<...>]`|[Atributos](../attributes.md)|<ul><li>Delimita un atributo.<br /></li></ul>|
|`\`|[Cadenas](../strings.md)|<ul><li>Produce el escape del carácter siguiente; se utiliza en los literales de carácter y de cadena.<br /></li></ul>|
|`^`|[Parámetros de tipo resueltos estáticamente](../generics/statically-resolved-type-parameters.md)<br /><br />[Cadenas](../strings.md)|<ul><li>Especifica los parámetros de tipo que deben resolverse en tiempo de compilación, no en runtime.<br /></li><li>Concatena cadenas.<br /></li></ul>|
|`^^^`|[Operadores bit a bit](bitwise-operators.md)|<ul><li>Calcula la operación OR exclusiva bit a bit.<br /></li></ul>|
|`_`|[Expresiones de coincidencia](../match-expressions.md)<br /><br />[Genéricos](../generics/index.md)|<ul><li>Indica un patrón de carácter comodín.<br /></li><li>Especifica un parámetro genérico anónimo.<br /></li></ul>|
|<code>&#96;</code>|[Generalización automática](../generics/automatic-generalization.md)|<ul><li>Se utiliza internamente para indicar un parámetro de tipo genérico.<br /></li></ul>|
|`{...}`|[Secuencias](../sequences.md)<br /><br />[Registros](../records.md)|<ul><li>Delimita expresiones de secuencia y expresiones de cálculo.<br /></li><li>Se utiliza en definiciones de registro.<br /></li></ul>|
|<code>&#124;</code>|[Expresiones de coincidencia](../match-expressions.md)|<ul><li>Delimita casos de coincidencia individuales, casos de unión discriminada individuales y valores de la enumeración.<br /></li></ul>|
|<code>&#124;&#124;</code>|[Operadores booleanos](boolean-operators.md)|<ul><li>Calcula la operación OR booleana.<br /></li></ul>|
|<code>&#124;&#124;&#124;</code>|[Operadores bit a bit](bitwise-operators.md)|<ul><li>Calcula la operación OR bit a bit.<br /></li></ul>|
|<code>&#124;></code>|[Funciones](../functions/index.md)|<ul><li>Pasa el resultado del lado izquierdo a la función del lado derecho (operador de canalización hacia delante).<br /></li></ul>|
|<code>&#124;&#124;></code>|[Operadores.&#40; &#124;&#124;&#62; &#41;&#60;'T1,'T2,'U&#62; Función](https://msdn.microsoft.com/visualfsharpdocs/conceptual/operators.%5b-hh%5d-%5d%5b%27t1%2c%27t2%2c%27u%5d-function-%5bfsharp%5d)|<ul><li>Pasa la tupla de dos argumentos del lado izquierdo a la función del lado derecho.<br /></li></ul>|
|<code>&#124;&#124;&#124;></code>|[Operadores.&#40; &#124;&#124;&#124;&#62; &#41;&#60;'T1,'T2,'T3,'U&#62; Función](https://msdn.microsoft.com/visualfsharpdocs/conceptual/operators.%5b-hhh%5d-%5d%5b%27t1%2c%27t2%2c%27t3%2c%27u%5d-function-%5bfsharp%5d)|<ul><li>Pasa la tupla de tres argumentos del lado izquierdo a la función del lado derecho.<br /></li></ul>|
|`~~`|[Sobrecarga de operadores](../operator-overloading.md)|<ul><li>Se utiliza para declarar una sobrecarga para el operador unario de negación.<br /></li></ul>|
|`~~~`|[Operadores bit a bit](bitwise-operators.md)|<ul><li>Calcula la operación NOT bit a bit.<br /></li></ul>|
|`~-`|[Sobrecarga de operadores](../operator-overloading.md)|<ul><li>Se utiliza para declarar una sobrecarga para el operador unario menos.<br /></li></ul>|
|`~+`|[Sobrecarga de operadores](../operator-overloading.md)|<ul><li>Se utiliza para declarar una sobrecarga para el operador unario más.<br /></li></ul>|

## <a name="operator-precedence"></a>Prioridad de operadores

En la siguiente tabla se muestra, de menor a mayor, el orden de precedencia de operadores y otras palabras clave de expresiones del lenguaje F#. También se indica la asociatividad, si corresponde.

|Operador|asociatividad|
|--------|-------------|
|`as`|Right|
|`when`|Right|
|<code>&#124;</code> (canalización)|Left|
|`;`|Right|
|`let`|No asociativo|
|`function`, `fun`, `match`, `try`|No asociativo|
|`if`|No asociativo|
|`not`|Right|
|`->`|Right|
|`:=`|Right|
|`,`|No asociativo|
|`or`, <code>&#124;&#124;</code>|Left|
|`&`, `&&`|Left|
|`:>`, `:?>`|Right|
|`<`*op*, `>`*op*, `=`, <code>&#124;</code>*op*, `&`*op*, `&`<br /><br />(incluyendo `<<<`, `>>>`, <code>&#124;&#124;&#124;</code>, `&&&`)|Left|
|`^`*op*<br /><br />(incluyendo `^^^`)|Right|
|`::`|Right|
|`:?`|No asociativo|
|`-`*op*, `+`*op*|Se aplica a los usos de infijo de estos símbolos|
|`*`*op*, `/`*op*, `%`*op*|Left|
|`**`*op*|Right|
|`f x` (aplicación de función)|Left|
|<code>&#124;</code> (coincidencia de patrones)|Right|
|operadores de prefijo (`+`*op*, `-`*op*, `%`, `%%`, `&`, `&&`, `!`*op*, `~`*op*)|Left|
|`.`|Left|
|`f(x)`|Left|
|`f<`*tipos*`>`|Left|

F# es compatible con la sobrecarga de operadores personalizados. Esto significa que puede definir sus propios operadores. En la tabla anterior, *op* puede ser cualquier secuencia válida (posiblemente vacía) de caracteres de operador, ya sean integrados o definidos por el usuario. Por lo tanto, puede utilizar esta tabla para determinar qué secuencia de caracteres se utilizará para que un operador personalizado logre alcanzar el nivel deseado de precedencia. Los caracteres `.` iniciales se omiten cuando el compilador determina la precedencia.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](../index.md)
- [Sobrecarga de operadores](../operator-overloading.md)
