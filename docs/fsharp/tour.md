---
title: 'Paseo de F #.'
description: 'Examinar algunas de las características clave de la programación de idioma en este paseo le con ejemplos de código de F #.'
author: cartermp
ms.author: phcart
ms.date: 02/28/2018
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 6821c74827b928cdd0c5aff101be4f9103986e3e
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="tour-of-f"></a>Paseo de F #. #

Es la mejor manera de obtener información sobre F # leer y escribir código de F #.  En este artículo se actúe como un recorrido por algunas de las características claves del lenguaje F # y se ofrecen algunos fragmentos de código que se pueden ejecutar en su equipo.  Para obtener información acerca de cómo configurar un entorno de desarrollo, visite [Introducción](tutorials/getting-started/index.md).

Hay dos conceptos principales en F #: tipos y funciones.  Este paseo le resaltan las características del lenguaje que se dividen en estos dos conceptos.

## <a name="functions-and-modules"></a>Las funciones y módulos

Los elementos más fundamentales de cualquier programa de F # son ***funciones*** organizan en ***módulos***.  [Funciones](language-reference/functions/index.md) realizar el trabajo en entradas para generar salidas, y que estén organizadas en [módulos](language-reference/modules.md), que son la manera principal agrupar cosas en F #.  Se definen mediante la [ `let` enlace](language-reference/functions/let-bindings.md), que asigne un nombre a la función y definir sus argumentos.

[!code-fsharp[BasicFunctions](../../samples/snippets/fsharp/tour.fs#L101-L133)]

`let` los enlaces son también cómo enlazar un valor a un nombre, de forma similar a una variable en otros lenguajes.  `let` los enlaces son ***inmutable*** de forma predeterminada, lo que significa que una vez que una función o el valor se enlaza a un nombre, no puede modificarse en contexto.  Esto difiere de las variables en otros idiomas, que son ***mutable***, lo que significa que sus valores se puede cambiar en cualquier punto en el tiempo.  Si necesita un enlace mutable, puede usar `let mutable ...` sintaxis.

[!code-fsharp[Immutability](../../samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a>Números, valores booleanos y cadenas

Como un lenguaje de .NET Framework, F # admite el mismo subyacente [tipos primitivos](language-reference/primitive-types.md) que existen en. NET.

Le mostramos cómo varios tipos numéricos se representan en F #:

[!code-fsharp[Numbers](../../samples/snippets/fsharp/tour.fs#L49-L68)]

Este es qué valores booleanos y lógica condicional básica de realizar el siguiente aspecto:

[!code-fsharp[Bools](../../samples/snippets/fsharp/tour.fs#L142-L152)]

Y aquí es qué basic [cadena](language-reference/strings.md) manipulación el siguiente aspecto:

[!code-fsharp[Strings](../../samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a>Tuplas

[Tuplas](language-reference/tuples.md) son un importante en F #.  Son una agrupación de valores sin nombre pero ordenados, que se pueden tratar como valores propiamente dichos.  Pensar en ellos como valores que se agregan a partir de otros valores.  Tienen muchos usos, como forma cómoda devolver varios valores de una función o valores para algunos comodidad ad-hoc de agrupación.

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L186-L203)]

A partir de F # 4.1, también puede crear `struct` tuplas.  Estos también interactúan completamente con C# 7/Visual Basic 15 tuplas, que también son `struct` tuplas:

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L205-L218)]

Es importante tener en cuenta que, dado que `struct` tuplas son tipos de valor, no se puede convertir implícitamente para hacer referencia a tuplas, o viceversa.  Debe convertir explícitamente entre una tupla de referencia y struct.

## <a name="pipelines-and-composition"></a>Las canalizaciones y composición

Canalizar operadores (`|>`, `<|`, `||>`, `<||`, `|||>`, `<|||`) y operadores de composición (`>>` y `<<`) se utilizan ampliamente al procesar datos en F #.  Estos operadores son funciones que le permiten establecer "canalizaciones" de las funciones de una forma flexible.  En el ejemplo siguiente se describen cómo puede aprovechar las ventajas de estos operadores para crear una canalización funcional simple.

[!code-fsharp[Pipelines](../../samples/snippets/fsharp/tour.fs#L227-L300)]

El ejemplo anterior realiza uso de muchas características de F #, incluidas las funciones de procesamiento de lista, funciones de primera clase, y [aplicación parcial](language-reference/functions/index.md#partial-application-of-arguments).  Aunque una comprensión profunda de cada uno de esos conceptos puede convertirse en algo avanzada, debe quedar claro cómo fácilmente las funciones pueden utilizarse para procesar los datos al generar las canalizaciones.

## <a name="lists-arrays-and-sequences"></a>Listas, matrices y secuencias

Listas, matrices y las secuencias son tres tipos de colección principal en la biblioteca básica de F #.

[Enumera](language-reference/lists.md) son colecciones ordenadas e inmutables de elementos del mismo tipo.  Son listas vinculadas individualmente, lo que significa que están concebidos para la enumeración, pero una opción deficiente para el acceso aleatorio y concatenación si son de gran tamaño.  Esto contrasta con las listas en otros lenguajes populares, que normalmente no se usan una lista vinculada individualmente para representar listas.

[!code-fsharp[Lists](../../samples/snippets/fsharp/tour.fs#L309-L359)]

[Matrices](language-reference/arrays.md) son de tamaño fijo, *mutable* colecciones de elementos del mismo tipo.  Admiten el acceso aleatorio rápido de elementos y son más rápidas que F # listas porque son simplemente contiguos bloques de memoria.

[!code-fsharp[Arrays](../../samples/snippets/fsharp/tour.fs#L368-L407)]

[Las secuencias de](language-reference/sequences.md) son una serie lógica de elementos, todas del mismo tipo.  Se trata de un tipo más general de listas y matrices, con la posibilidad de la "vista" en cualquier serie lógica de elementos.  También se resaltan porque pueden estar ***diferida***, lo que significa que se pueden calcular elementos solo cuando sean necesarias.

[!code-fsharp[Sequences](../../samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a>Funciones recursivas

Procesamiento de colecciones o secuencias de elementos se suele realizar con [recursividad](language-reference/functions/index.md#recursive-functions) en F #.  Aunque F # admite la programación imperativa y bucles, recursividad es preferible porque es más fácil de garantizar la corrección.

>[!NOTE]
En el ejemplo siguiente se utiliza la coincidencia de patrones a través de la `match` expresión.  Esta construcción fundamental se trata más adelante en este artículo.

[!code-fsharp[RecursiveFunctions](../../samples/snippets/fsharp/tour.fs#L461-L500)]

F # también es totalmente compatible con optimización de llamadas de cola, que es una manera para optimizar las llamadas recursivas para que sean tan rápidos como una construcción de bucle.

## <a name="record-and-discriminated-union-types"></a>Registro y tipos de unión discriminada

Registro y tipos de unión son dos tipos de datos fundamentales que se utiliza en código de F # y suelen ser la mejor manera de representar datos en un programa en F #.  Aunque esto hace que sean similares a las clases en otros lenguajes, uno de sus principales diferencias es que tienen semántica de igualdad estructural.  Esto significa que son "de forma nativa" comparables e igualdad es sencilla: basta con comprobar si una es igual que la otra.

[Registros](language-reference/records.md) son un agregado de valores con nombre, con miembros opcionales (por ejemplo, los métodos).  Si está familiarizado con C# o Java, a continuación, estos se sentirá similares a POCOs o POJOs - solo con igualdad estructural y menos ceremonia.

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L507-L559)]

A partir de F # 4.1, también puede representar como `struct`s.  Esto se realiza con el `[<Struct>]` atributo:

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L561-L568)]

[(Adeudados) uniones discriminadas](language-reference/discriminated-unions.md) son valores que pudieron ser un número de casos o de formularios con nombre.  Datos almacenados en el tipo pueden ser uno de varios valores distintos.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L575-L631)]

También puede usar adeudados como *uniones discriminadas de caso único*, para ayudar a los tipos primitivos de modelado de dominios.  A menudo, las cadenas y otros tipos primitivos se usan para representar algo y, por tanto, tienen un significado determinado.  Sin embargo, utilizando solo la representación primitiva de los datos puede dar lugar a erróneamente asignar un valor incorrecto.  Que representa cada tipo de información que una unión de caso único distinta puede aplicar la corrección en este escenario.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L633-L654)]

Como se muestra en el ejemplo anterior, para obtener el valor subyacente en un único caso discriminada Union, debe liberar explícitamente.

Además, adeudados también admiten las definiciones recursivas, lo que permite representar fácilmente árboles e inherentemente datos recursivos.  Por ejemplo, mostramos cómo puede representar un árbol de búsqueda binario con `exists` y `insert` funciones.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L656-L683)]

Porque adeudados permiten representar la estructura recursiva del árbol en el tipo de datos, en funcionamiento en esta estructura recursiva es sencillo y garantiza la corrección.  También se admite en la coincidencia de patrones, tal y como se muestra a continuación.

Además, puede representar adeudados como `struct`s con el `[<Struct>]` atributo:

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L685-L696)]

Sin embargo, hay dos conceptos clave que hay que tener en cuenta al hacerlo:

1. No puede ser un struct DU definidos de forma recursiva.
2. Un struct DU debe tener nombres únicos para cada uno de sus casos.

Si debe seguir los pasos anteriores, provocará un error de compilación.

## <a name="pattern-matching"></a>Coincidencia de modelos

[Coincidencia de patrón](language-reference/pattern-matching.md) es la característica de lenguaje F # que permite la corrección para el funcionamiento de los tipos de F #.  En los ejemplos anteriores, probablemente ha observado un poco de `match x with ...` sintaxis.  Esta construcción permite que el compilador, que puede entender la "forma" de los tipos de datos, para exigir el uso para tener en cuenta todos los casos posibles cuando se usa un tipo de datos a través de lo que se conoce como coincidencia de patrones exhaustiva.  Esto es extremadamente eficaz para la exactitud e inteligentemente sirve para "aumentar" lo que normalmente sería un problema de tiempo de ejecución en tiempo de compilación.

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L705-L739)]

También puede utilizar la forma abreviada `function` construcción de coincidencia de patrones, lo que resulta útil al escribir funciones que hacen usan de [aplicación parcial](language-reference/functions/index.md#partial-application-of-arguments):

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L741-L759)]

Algo que quizás haya observado es el uso de la `_` patrón.  Esto se conoce como el [patrón de carácter comodín](language-reference/pattern-matching.md#wildcard-pattern), que es una manera de decir "no les importa qué algo".  Aunque es útil, puede omitir accidentalmente la coincidencia de patrones exhaustiva y ya no se beneficiarán de exigencias de tiempo de compilación si no tiene cuidado en uso `_`.  Mejor se usa cuando no le interesa determinadas partes de un tipo descompuesto coincidencia o la última cláusula cuando ha enumerado todos los casos significativos en una expresión de coincidencia de patrón cuando.

[Modelos activos](language-reference/active-patterns.md) son otra construcción eficaz para usar con la coincidencia de patrones.  Le permiten dividir los datos de entrada en formularios personalizados, descomposición de ellos en el sitio de llamada de coincidencia de patrón.  Puede también se pueden parametrizar, lo que permite definir la partición como una función.  Al expandir el ejemplo anterior para admitir modelos activos es algo parecido a esto:

[!code-fsharp[ActivePatterns](../../samples/snippets/fsharp/tour.fs#L761-L783)]

## <a name="optional-types"></a>Tipos opcionales

Un caso especial de tipos de unión discriminada es el tipo de opción, lo cual resulta útil que forma parte de la biblioteca básica de F #.

[El tipo de opción](language-reference/options.md) es un tipo que representa uno de estos dos casos: un valor, o nada en absoluto.  Se utiliza en cualquier escenario donde un valor posible o no puede deberse a una operación determinada.  A continuación, esto obliga a la cuenta en ambos casos, lo que constituye un problema de tiempo de compilación en lugar de un problema de tiempo de ejecución.  A menudo se utilizan en las API donde `null` se utiliza para representar "nothing" en su lugar, lo que elimina la necesidad de preocuparse `NullReferenceException` en muchas circunstancias.

[!code-fsharp[Options](../../samples/snippets/fsharp/tour.fs#L791-L811)]

## <a name="units-of-measure"></a>Unidades de medida

Una característica única del sistema de tipos de F # es la capacidad para proporcionar contexto para literales numéricos a través de unidades de medida.

[Unidades de medida](language-reference/units-of-measure.md) le permiten asociar un tipo numérico a una unidad, por ejemplo, metros, y haber funciones realizan el trabajo en unidades en lugar de literales numéricos.  Esto permite al compilador comprobar que los tipos de literales numéricos que se pasan en sentido en un contexto determinado, lo que elimina los errores en tiempo de ejecución asociada a ese tipo de trabajo.

[!code-fsharp[UnitsOfMeasure](../../samples/snippets/fsharp/tour.fs#L818-L839)]

La biblioteca básica de F # define muchos tipos de unidades SI y conversiones de unidades.  Para obtener más información, consulte el [Microsoft.FSharp.Data.UnitSystems.SI Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d).

## <a name="classes-and-interfaces"></a>Las clases e Interfaces

F # también es totalmente compatible con las clases. NET, [Interfaces](language-reference/interfaces.md), [clases abstractas](language-reference/abstract-classes.md), [herencia](language-reference/inheritance.md), y así sucesivamente.

[Clases de](language-reference/classes.md) son tipos que representan objetos. NET, que puede tener propiedades, métodos y eventos como su [miembros](language-reference/members/index.md).

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L848-L877)]

También es muy sencillo definir clases genéricas.

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L884-L905)]

Para implementar una interfaz, puede usar `interface ... with` sintaxis o un [expresión de objeto](language-reference/object-expressions.md).

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L912-L931)]

## <a name="which-types-to-use"></a>Los tipos que se utilizan

La presencia de tuplas, registros, uniones discriminadas y clases conduce a una pregunta importante: ¿cuál debería utilizar?  Al igual que casi todos los elementos en la vida, la respuesta depende de sus circunstancias.

Tuplas son excelentes para devolver varios valores desde una función y el uso de un agregado ad-hoc de valores como un valor en Sí.

Los registros son "nivel superior" tuplas, tener denominado etiquetas y la compatibilidad con miembros opcionales.  Únicamente son excelentes para obtener una representación de la ceremonia de baja de datos en tránsito a través de su programa.  Dado que tienen igualdad estructural, es fácil de usar con la comparación.

Uniones discriminadas tienen muchos usos, pero la ventaja principal es poder utilizarlas junto con la coincidencia de patrones para tener en cuenta todas las posibles "formas" que pueden tener datos.  

Las clases son excelentes para un gran número de razones, como cuando se necesita representar la información y también asociar esa información a la funcionalidad.  Como regla general, si tiene la funcionalidad que está vinculada conceptualmente a algunos datos, utilizando las clases y los principios de programación orientada a objetos es una gran ventaja.  Las clases son también el tipo de datos preferido cuando se interopera con C# y Visual Basic, como estos idiomas utilizan clases para casi todo.

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha visto algunas de las características principales del lenguaje, estará preparado para escribir sus primera programas de F #.  Extraer del repositorio [Introducción](tutorials/getting-started/index.md) para obtener información sobre cómo configurar el entorno de desarrollo y escribir código.

Los pasos siguientes para obtener más pueden ser el que desee, pero se recomienda [funciona como valores de primera clase](introduction-to-functional-programming/functions-as-first-class-values.md) <!--[Introduction to Functional Programming in F#](introduction-to-functional-programming/index.md)--> obtener familiarizado con conceptos de programación funcionales principales.  Estos serán esenciales en la compilación de programas sólidos en F #.

Asimismo, consulte la [referencia del lenguaje F #](language-reference/index.md) para ver una completa colección de contenido conceptual en F #.
