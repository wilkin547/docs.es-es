---
title: Paseo por F#
description: Examine algunas de las características claves del lenguaje en esta visita con ejemplos de código de programación F#.
ms.date: 11/06/2018
ms.openlocfilehash: 64394342777003b33dd77028739fb7209b9f3c86
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301251"
---
# <a name="tour-of-f"></a>Paseo por F\#

Es la mejor manera para obtener información sobre F# leer y escribir código de F#. En este artículo actuará como un paseo por algunas de las características clave del lenguaje F# y proporcionarle algunos fragmentos de código que se pueden ejecutar en el equipo. Para obtener información acerca de cómo configurar un entorno de desarrollo, visite [Introducción](tutorials/getting-started/index.md).

Hay dos conceptos principales en F#: tipos y funciones.  Este paseo realzan características del lenguaje que se dividen en estas dos conceptos.

## <a name="executing-the-code-online"></a>Ejecutar el código en línea

Si no tienes F# instalado en el equipo, puede ejecutar todos los ejemplos en el explorador con [intente F# en WebAssembly](https://tryfsharp.fsbolero.io/). Fable es un dialecto de F# que se ejecuta directamente en el explorador. Para ver los ejemplos que siguen en la replicación, consulte **ejemplos > más información > paseo F#**  en la barra de menú de la izquierda de la REPL Fable.

## <a name="functions-and-modules"></a>Funciones y módulos

Las partes más fundamentales de cualquier programa de F# son ***funciones*** organizados ***módulos***.  [Funciones](language-reference/functions/index.md) realizar trabajo en las entradas para producir salidas, y se organizan en [módulos](language-reference/modules.md), que son la principal forma Agrupar cosas en F#.  Se definen mediante la [ `let` enlace](language-reference/functions/let-bindings.md), que asigne un nombre de la función y definir sus argumentos.

[!code-fsharp[BasicFunctions](../../samples/snippets/fsharp/tour.fs#L101-L133)]

`let` los enlaces son también cómo enlazar un valor a un nombre, similar a una variable en otros idiomas.  `let` los enlaces son ***inmutable*** de forma predeterminada, lo que significa que una vez que un valor o una función está enlazada a un nombre, no se puede cambiar en contexto.  Esto difiere de las variables en otros lenguajes, que son ***mutable***, lo que significa que sus valores se puede cambiar en cualquier momento en el tiempo.  Si necesita un enlace mutable, puede usar `let mutable ...` sintaxis.

[!code-fsharp[Immutability](../../samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a>Números, booleanos y cadenas

Como un lenguaje. NET, F# es compatible con el mismo subyacente [tipos primitivos](language-reference/primitive-types.md) que existen en. NET.

Le mostramos cómo varios tipos numéricos se representan en F#:

[!code-fsharp[Numbers](../../samples/snippets/fsharp/tour.fs#L49-L68)]

Aquí es qué valores booleanos y realizar lógica condicional básica es similar:

[!code-fsharp[Bools](../../samples/snippets/fsharp/tour.fs#L142-L152)]

Y aquí es qué basic [cadena](language-reference/strings.md) manipulación el siguiente aspecto:

[!code-fsharp[Strings](../../samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a>Tuplas

[Las tuplas](language-reference/tuples.md) son un componente indispensable en F#.  Son una agrupación de valores sin nombre pero ordenados, que se pueden tratar como valores propiamente dichos.  Piense en ellas como valores que se agregan a partir de otros valores.  Tienen muchos usos, como forma cómoda devolver varios valores de una función o agrupación de valores para alguna comodidad ad hoc.

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L186-L203)]

A partir de F# 4.1, también se puede crear `struct` tuplas.  Estos también interoperan completamente con tuplas de C# 7 o Visual Basic 15, que también son `struct` tuplas:

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L205-L218)]

Es importante tener en cuenta que dado que `struct` las tuplas son tipos de valor, no se puede convertir implícitamente para hacer referencia a las tuplas, o viceversa.  Debe convertir explícitamente entre una tupla de referencia y struct.

## <a name="pipelines-and-composition"></a>Las canalizaciones y la composición

Operadores de canalización, como `|>` se usan ampliamente al procesar datos en F#. Estos operadores son funciones que permiten establecer "canalizaciones" de las funciones de una manera flexible. El ejemplo siguiente se guiará a través de cómo puede aprovechar estos operadores para crear una canalización simple funcional:

[!code-fsharp[Pipelines](../../samples/snippets/fsharp/tour.fs#L227-L282)]

El ejemplo anterior realiza el uso de muchas características de F#, incluidas las funciones de procesamiento de lista, las funciones de primera clase, y [aplicación parcial](language-reference/functions/index.md#partial-application-of-arguments). Aunque un profundo conocimiento de cada uno de esos conceptos puede convertirse en algo avanzado, debe quedar claro cómo fácilmente funciones se pueden usar para procesar los datos al compilar las canalizaciones.

## <a name="lists-arrays-and-sequences"></a>Las listas, matrices y secuencias

Las listas, matrices y las secuencias son tres tipos de colección principal en la biblioteca básica de F#.

[Enumera](language-reference/lists.md) son colecciones ordenadas e inmutables de elementos del mismo tipo.  Son listas vinculadas individualmente, lo que significa que están diseñados para la enumeración, pero una mala elección para el acceso aleatorio y concatenación si son grandes.  Esto contrasta con las listas en otros lenguajes populares, que normalmente no utilizan una lista vinculada individualmente para representar listas.

[!code-fsharp[Lists](../../samples/snippets/fsharp/tour.fs#L309-L359)]

[Matrices](language-reference/arrays.md) son de tamaño fijo, *mutable* las colecciones de elementos del mismo tipo.  Se admiten el acceso aleatorio rápido de elementos y son más rápidas que F# listas porque son simplemente contiguos bloques de memoria.

[!code-fsharp[Arrays](../../samples/snippets/fsharp/tour.fs#L368-L407)]

[Las secuencias de](language-reference/sequences.md) son una serie lógica de elementos, todos del mismo tipo.  Se trata de un tipo más general que las listas y matrices, puede ser la "vista" en cualquier serie lógica de elementos.  También destacarse porque pueden estar ***diferida***, lo que significa que se pueden calcular los elementos solo cuando sean necesarios.

[!code-fsharp[Sequences](../../samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a>Funciones recursivas

Procesamiento de colecciones o secuencias de elementos se suele realizar con [recursividad](language-reference/functions/index.md#recursive-functions) en F#.  Aunque F# tiene compatibilidad con bucles y la programación imperativa, recursividad es preferible porque es más fácil de garantizar la corrección.

> [!NOTE]
> El ejemplo siguiente se usa la coincidencia de patrones a través de la `match` expresión.  Esta construcción fundamental se trata más adelante en este artículo.

[!code-fsharp[RecursiveFunctions](../../samples/snippets/fsharp/tour.fs#L461-L500)]

F# también tiene compatibilidad total para la optimización de llamar al final, que es una forma de optimizar las llamadas recursivas para que sean tan rápidos como una construcción de bucle.

## <a name="record-and-discriminated-union-types"></a>Registro y los tipos de unión Discriminados

Registro y tipos de unión son dos tipos de datos fundamentales utilizados en el código de F# y suelen ser la mejor manera de representar los datos en un programa de F#.  Aunque esto hace que sean similares a las clases en otros lenguajes, una de las principales diferencias es que tienen semántica de igualdad estructural.  Esto significa que son comparables "de forma nativa" y de igualdad es sencilla: basta con comprobar si una es igual a otro.

[Registros](language-reference/records.md) son un agregado de los valores con nombre, con miembros opcionales (por ejemplo, métodos).  Si está familiarizado con C# o Java, a continuación, estos deberían sentir similares a poco o POJO - solo con igualdad estructural y menos complejidad.

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L507-L559)]

A partir de F# 4.1, también puede representar los registros marcados como `struct`s.  Esto se realiza con el `[<Struct>]` atributo:

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L561-L568)]

[(Adeudados) uniones discriminadas](language-reference/discriminated-unions.md) son valores que podrían ser un número de casos o de formularios con nombre.  Datos almacenados en el tipo pueden ser uno de varios valores distintos.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L575-L631)]

También puede usar adeudados como *solo caso las uniones discriminadas*, para ayudar a través de los tipos primitivos de modelado de dominios.  A menudo, las cadenas y otros tipos primitivos se utilizan para representar algo y, por tanto, tienen un significado concreto.  Sin embargo, utilizando solo la representación de primitiva de los datos puede dar lugar a erróneamente asignar un valor incorrecto.  Que representa cada tipo de información como una unión de caso único distintiva puede aplicar la corrección en este escenario.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L633-L654)]

Como se muestra en el ejemplo anterior, para obtener el valor subyacente de un solo caso unión discriminada, debe liberar explícitamente.

Además, adeudados también admiten definiciones recursivas, lo que permite representar fácilmente árboles e inherentemente datos recursivos.  Por ejemplo, mostramos cómo puede representar un árbol de búsqueda binario con `exists` y `insert` funciones.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L656-L683)]

Porque adeudados permiten representar la estructura recursiva del árbol en el tipo de datos, operan en esta estructura recursiva es sencillo y garantiza la exactitud.  También se admite en la coincidencia de patrones, como se muestra a continuación.

Además, puede representar adeudados como `struct`s con el `[<Struct>]` atributo:

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L685-L696)]

Sin embargo, hay dos conceptos clave que hay que tener en cuenta al hacerlo:

1. No puede ser un struct DU definidos de forma recursiva.
2. Un struct DU debe tener nombres únicos para cada uno de sus casos.

Si no sigue los pasos anteriores se producirá un error de compilación.

## <a name="pattern-matching"></a>Coincidencia de modelos

[Coincidencia de patrón](language-reference/pattern-matching.md) es la característica del lenguaje F# que permite la corrección para operar en tipos de F#.  En los ejemplos anteriores, probablemente ha observado un poco de `match x with ...` sintaxis.  Esta construcción permite que el compilador, que puede conocer la "forma" de los tipos de datos, para forzar que tener en cuenta todos los casos posibles cuando se usa un tipo de datos a través de lo que se conoce como coincidencia de patrones exhaustiva.  Esto es increíblemente eficaz es correcto y se puede usar inteligentemente para "alzan" lo que normalmente sería un problema en tiempo de ejecución en tiempo de compilación.

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L705-L742)]

Algo que quizás haya observado es el uso de la `_` patrón.  Esto se conoce como el [patrón comodín](language-reference/pattern-matching.md#wildcard-pattern), que es una manera de decir "No me importa algo What ' s".  Aunque es útil, puede omitir accidentalmente la coincidencia de patrones exhaustiva y ya no beneficiarse de las exigencias de tiempo de compilación si no tiene cuidado en utilizando `_`.  Se usa preferiblemente cuando no le interesa ciertas partes de un tipo descompuesto al patrón coincidente, o en la cláusula final cuando ha enumerado todos los casos significativos en una expresión de coincidencia.

[Modelos activos](language-reference/active-patterns.md) son otra construcción eficaces para usar con coincidencia de patrones.  Le permiten dividir los datos de entrada en los formularios personalizados, descomponerlas en el sitio de llamada de coincidencia de patrón.  También se pueden parametrizar, lo que permite definir la partición como una función.  Ampliación del ejemplo anterior para admitir modelos activos es algo parecido a esto:

[!code-fsharp[ActivePatterns](../../samples/snippets/fsharp/tour.fs#L764-L786)]

## <a name="optional-types"></a>Tipos de opcionales

Un caso especial de tipos de unión discriminada es el tipo de opción, que es tan útil que forma parte de la biblioteca básica de F#.

[El tipo de opción](language-reference/options.md) es un tipo que representa uno de los dos casos: un valor o nada en absoluto.  Se utiliza en cualquier escenario donde un valor puede o no puede deberse a una operación determinada.  A continuación, esto obliga a cuenta para ambos casos, lo que constituye un problema de tiempo de compilación en lugar de un problema de tiempo de ejecución.  A menudo se usan en las API donde `null` se utiliza para representar "nothing" en su lugar, lo que elimina la necesidad de preocuparse por `NullReferenceException` en muchas circunstancias.

[!code-fsharp[Options](../../samples/snippets/fsharp/tour.fs#L789-L814)]

## <a name="units-of-measure"></a>Unidades de medida

Una característica exclusiva de sistema de tipos de F# es la capacidad para proporcionar contexto para literales numéricos a través de las unidades de medida.

[Las unidades de medida](language-reference/units-of-measure.md) le permiten asociar un tipo numérico a una unidad, como metros, y dispone de funciones de realizar el trabajo en unidades en lugar de literales numéricos.  Esto permite al compilador comprobar que los tipos de literales numéricos que se pasa en el sentido en un contexto determinado, lo que elimina los errores en tiempo de ejecución asociado con ese tipo de trabajo.

[!code-fsharp[UnitsOfMeasure](../../samples/snippets/fsharp/tour.fs#L817-L842)]

La biblioteca básica de F# define muchos tipos de unidad del SI y conversiones de unidades.  Para obtener más información, consulte el [Microsoft.FSharp.Data.UnitSystems.SI Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d).

## <a name="classes-and-interfaces"></a>Las clases e Interfaces

F# también es totalmente compatible con las clases. NET, [Interfaces](language-reference/interfaces.md), [clases abstractas](language-reference/abstract-classes.md), [herencia](language-reference/inheritance.md), y así sucesivamente.

[Las clases](language-reference/classes.md) son tipos que representan objetos. NET, que puede tener propiedades, métodos y eventos como su [miembros](language-reference/members/index.md).

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L845-L880)]

Definir las clases genéricas también es muy sencillo.

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L883-L908)]

Para implementar una interfaz, puede usar `interface ... with` sintaxis o un [expresión de objeto](language-reference/object-expressions.md).

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L911-L934)]

## <a name="which-types-to-use"></a>Los tipos de uso

La presencia de tuplas, uniones discriminadas, registros y clases conduce a una pregunta importante: ¿cuál debiera usar?  Al igual que casi todo lo que en la vida, la respuesta depende de sus circunstancias.

Las tuplas son excelentes para devolver varios valores de una función y el uso de un agregado ad hoc de los valores como un valor en Sí.

Los registros son "nivel superior" tuplas, tener denominado etiquetas y la compatibilidad con miembros opcionales.  Son ideales para una representación informal de datos en tránsito a través de su programa.  Porque tienen igualdad estructural, son fáciles de usar con la comparación.

Las uniones discriminadas tienen muchos usos, pero la ventaja principal es poder usarlos junto con la coincidencia de patrones para tener en cuenta todas las posibles "formas" que puede tener una de datos.  

Las clases son excelentes para un gran número de razones, como cuando se necesita representar la información y también enlazar esa información a la funcionalidad.  Como regla general, cuando se dispone de funcionalidad que está asociada conceptualmente a algunos datos, utilizando las clases y los principios de programación orientada a objetos es una gran ventaja.  Las clases también son el tipo de datos preferida cuando se interopera con C# y Visual Basic, como estos lenguajes usar clases para casi todo.

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha visto algunas de las principales características del lenguaje, debería estar listo para escribir sus primeros programas de F#!  Desproteger [Introducción](tutorials/getting-started/index.md) para obtener información sobre cómo configurar el entorno de desarrollo y escribir algo de código.

Los pasos siguientes para obtener más pueden ser el que desee, pero se recomienda [Introducción a la programación funcional en F# ](introduction-to-functional-programming/index.md) para comenzar a familiarizarse con los conceptos de programación funcional.  Estos serán esenciales en la creación de programas sólidos en F#.

Además, revise el [referencia del lenguaje F#](language-reference/index.md) para ver una colección completa de contenido conceptual en F#.
