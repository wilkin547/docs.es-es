---
title: Paseo por F#
description: 'Examine algunas de las características clave del lenguaje de programación de F # en este paseo con ejemplos de código.'
ms.date: 08/14/2020
ms.openlocfilehash: b115317e1f47ef7e18333cae4145b99e11645579
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558600"
---
# <a name="tour-of-f"></a>Paseo por F\#

La mejor manera de obtener información sobre F # es leer y escribir código de F #. Este artículo le servirá de guía a través de algunas de las características clave del lenguaje F # y le proporcionará algunos fragmentos de código que puede ejecutar en la máquina. Para obtener información sobre cómo configurar un entorno de desarrollo, consulte [Introducción](get-started/index.md).

Hay dos conceptos principales en F #: funciones y tipos.  En este paseo se resaltan las características del lenguaje que se encuentran en estos dos conceptos.

## <a name="executing-the-code-online"></a>Ejecutar el código en línea

Si no tiene F # instalado en el equipo, puede ejecutar todos los ejemplos en el explorador con [try f # en Webassembly](https://tryfsharp.fsbolero.io/). Fable es un dialecto de F # que se ejecuta directamente en el explorador. Para ver los ejemplos que se indican a continuación en el REPL, consulte los **ejemplos > aprenda > paseo por F #** en la barra de menús de la izquierda de Fable repl.

## <a name="functions-and-modules"></a>Funciones y módulos

Las partes más fundamentales de cualquier programa de F # son ***funciones*** organizadas en ***módulos***.  [Las funciones](./language-reference/functions/index.md) realizan trabajos en entradas para generar salidas y se organizan en [módulos](./language-reference/modules.md), que son la manera principal de agrupar elementos en F #.  Se definen mediante el [ `let` enlace](./language-reference/functions/let-bindings.md), que asigna un nombre a la función y definen sus argumentos.

[!code-fsharp[BasicFunctions](~/samples/snippets/fsharp/tour.fs#L101-L133)]

`let` los enlaces también son cómo enlazar un valor a un nombre, de forma similar a una variable en otros lenguajes.  `let` los enlaces son ***inmutables*** de forma predeterminada, lo que significa que una vez que un valor o una función se enlaza a un nombre, no se puede cambiar en contexto.  Esto contrasta con las variables de otros lenguajes, que son ***mutables***, lo que significa que sus valores se pueden cambiar en cualquier momento en el tiempo.  Si necesita un enlace mutable, puede usar la `let mutable ...` Sintaxis.

[!code-fsharp[Immutability](~/samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a>Números, valores booleanos y cadenas

Como lenguaje .NET, F # admite los mismos [tipos primitivos](language-reference/basic-types.md) subyacentes que existen en .net.

Este es el modo en que se representan varios tipos numéricos en F #:

[!code-fsharp[Numbers](~/samples/snippets/fsharp/tour.fs#L49-L68)]

Estos son los valores booleanos y la lógica condicional básica tiene el siguiente aspecto:

[!code-fsharp[Bools](~/samples/snippets/fsharp/tour.fs#L142-L152)]

Y este es el aspecto básico de la manipulación de [cadenas](./language-reference/strings.md) :

[!code-fsharp[Strings](~/samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a>Tuplas

Las [tuplas](./language-reference/tuples.md) son una gran cantidad de F #.  Son una agrupación de valores sin nombre, pero ordenados, que se pueden tratar como propios valores.  Considérelos como valores que se agregan a partir de otros valores.  Tienen muchos usos, como la devolución cómoda de varios valores de una función o la agrupación de valores para una conveniencia ad hoc.

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L186-L203)]

También puede crear `struct` tuplas.  También interoperan totalmente con las tuplas de C# 7/Visual Basic 15, que también son `struct` tuplas:

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L205-L218)]

Es importante tener en cuenta que, dado que las `struct` tuplas son tipos de valor, no se pueden convertir implícitamente en tuplas de referencia, o viceversa.  Debe convertir explícitamente entre una tupla de referencia y struct.

## <a name="pipelines-and-composition"></a>Canalizaciones y composición

Los operadores de canalización como `|>` se usan en gran medida al procesar los datos en F #. Estos operadores son funciones que permiten establecer "canalizaciones" de funciones de una manera flexible. En el ejemplo siguiente se describe cómo puede aprovechar estos operadores para crear una canalización funcional sencilla:

[!code-fsharp[Pipelines](~/samples/snippets/fsharp/tour.fs#L227-L282)]

En el ejemplo anterior se utilizaban muchas características de F #, incluidas las funciones de procesamiento de lista, las funciones de primera clase y la [aplicación parcial](./language-reference/functions/index.md#partial-application-of-arguments). Aunque una comprensión profunda de cada uno de estos conceptos puede ser un poco más avanzada, debe estar claro cómo se pueden usar las funciones para procesar datos al crear canalizaciones.

## <a name="lists-arrays-and-sequences"></a>Listas, matrices y secuencias

Las listas, matrices y secuencias son tres tipos de colección principales en la biblioteca básica de F #.

[Las listas](./language-reference/lists.md) son colecciones ordenadas e inmutables de elementos del mismo tipo.  Se trata de listas vinculadas individualmente, lo que significa que están pensadas para la enumeración, pero es una opción deficiente para el acceso aleatorio y la concatenación si son grandes.  Esto contrasta con las listas de otros lenguajes populares, que normalmente no usan una lista vinculada individualmente para representar listas.

[!code-fsharp[Lists](~/samples/snippets/fsharp/tour.fs#L309-L359)]

Las [matrices](./language-reference/arrays.md) son colecciones *mutables* de tamaño fijo de elementos del mismo tipo.  Admiten el acceso aleatorio rápido de los elementos y son más rápidos que las listas de F # porque son simplemente bloques de memoria contiguos.

[!code-fsharp[Arrays](~/samples/snippets/fsharp/tour.fs#L368-L407)]

Las [secuencias](./language-reference/sequences.md) son una serie lógica de elementos, todo del mismo tipo.  Se trata de un tipo más general que las listas y matrices, capaz de ser su "vista" en cualquier serie lógica de elementos.  También destacan porque pueden ser ***Lazy***, lo que significa que los elementos solo se pueden calcular cuando son necesarios.

[!code-fsharp[Sequences](~/samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a>Funciones recursivas

El procesamiento de colecciones o secuencias de elementos se realiza normalmente con [recursividad](./language-reference/functions/index.md#recursive-functions) en F #.  Aunque F # es compatible con los bucles y la programación imperativa, se prefiere la recursividad porque es más fácil garantizar la corrección.

> [!NOTE]
> En el ejemplo siguiente se usa la coincidencia de patrones a través de la `match` expresión.  Esta construcción fundamental se trata más adelante en este artículo.

[!code-fsharp[RecursiveFunctions](~/samples/snippets/fsharp/tour.fs#L461-L500)]

F # también tiene compatibilidad total con la optimización de llamadas de cola, que es una manera de optimizar las llamadas recursivas de modo que sean tan rápidas como una construcción de bucle.

## <a name="record-and-discriminated-union-types"></a>Tipos de unión de registro y discriminado

Los tipos de registro y de Unión son dos tipos de datos fundamentales que se usan en el código de F # y, por lo general, son la mejor manera de representar los datos en un programa de F #.  Aunque esto hace que sean similares a las clases de otros lenguajes, una de sus principales diferencias es que tienen una semántica de igualdad estructural.  Esto significa que se comparan de forma "nativa" y la igualdad es sencilla. Compruebe si uno es igual que el otro.

[Los registros](./language-reference/records.md) son un agregado de valores con nombre, con miembros opcionales (como métodos).  Si está familiarizado con C# o Java, estos deberían ser similares a POCO o POJO, solo con igualdad estructural y menos ceremonia.

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L507-L559)]

También puede representar registros como Structs. Esto se hace con el `[<Struct>]` atributo:

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L561-L568)]

Las [uniones discriminadas (DUs)](./language-reference/discriminated-unions.md) son valores que pueden ser una serie de formularios o casos con nombre.  Los datos almacenados en el tipo pueden tener uno de varios valores distintos.

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L575-L631)]

También puede usar DUs como *uniones discriminadas de un solo caso*para ayudar con el modelado de dominios a través de tipos primitivos.  A menudo, las veces, las cadenas y otros tipos primitivos se utilizan para representar algo y, por tanto, se les da un significado determinado.  Sin embargo, el uso de la representación primitiva de los datos puede dar lugar a la asignación errónea de un valor incorrecto.  Representar cada tipo de información como una Unión de un solo caso distinto puede exigir una corrección en este escenario.

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L633-L654)]

Como se muestra en el ejemplo anterior, para obtener el valor subyacente en una Unión discriminada de un solo caso, debe desencapsularlo explícitamente.

Además, DUs también admite definiciones recursivas, lo que le permite representar fácilmente árboles y datos recursivos de forma inherente.  Por ejemplo, aquí se muestra cómo se puede representar un árbol de búsqueda binario con `exists` `insert` funciones y.

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L656-L683)]

Dado que DUs le permite representar la estructura recursiva del árbol en el tipo de datos, el funcionamiento de esta estructura recursiva es sencillo y garantiza la corrección.  También se admite en la coincidencia de patrones, como se muestra a continuación.

Además, puede representar DUs como `struct` s con el `[<Struct>]` atributo:

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L685-L696)]

Sin embargo, hay dos aspectos clave que hay que tener en cuenta al hacerlo:

1. No se puede definir un struct DU de forma recursiva.
2. Una estructura DU debe tener nombres únicos para cada uno de sus casos.

Si no se sigue el anterior, se producirá un error de compilación.

## <a name="pattern-matching"></a>Coincidencia de modelos

La [coincidencia de patrones](./language-reference/pattern-matching.md) es la característica del lenguaje f #, que permite la corrección del funcionamiento en tipos de F #.  En los ejemplos anteriores, probablemente detectó bastante `match x with ...` Sintaxis.  Esta construcción permite al compilador, que puede comprender la "forma" de los tipos de datos, para obligarle a tener en cuenta todos los casos posibles al usar un tipo de datos a través de lo que se conoce como coincidencia de patrones exhaustiva.  Esto es increíblemente eficaz para corregir y se puede usar de forma inteligente para "levantar" lo que normalmente sería un problema de tiempo de ejecución en tiempo de compilación.

[!code-fsharp[PatternMatching](~/samples/snippets/fsharp/tour.fs#L705-L742)]

Algo que puede haber observado es el uso del `_` patrón.  Esto se conoce como el [patrón de carácter comodín](./language-reference/pattern-matching.md#wildcard-pattern), que es una forma de decir "no me importa qué es algo".  Aunque es práctico, puede omitir accidentalmente la coincidencia de patrones exhaustivas y dejar de beneficiarse de las impuestas en tiempo de compilación si no tiene cuidado al usar `_` .  Se recomienda usar cuando no le interesan ciertas partes de un tipo descompuesto al buscar coincidencias de patrones o la cláusula final cuando ha enumerado todos los casos significativos en una expresión de coincidencia de patrones.

En el ejemplo siguiente, el `_` caso se usa cuando se produce un error en una operación de análisis.

[!code-fsharp[PatternMatching](~/samples/snippets/fsharp/tour.fs#L744-L762)]

Los [modelos activos](./language-reference/active-patterns.md) son otra construcción eficaz que se usa con la coincidencia de patrones.  Permiten particionar los datos de entrada en formularios personalizados, descomponerlos en el sitio de llamada de coincidencia de patrones.  También se pueden parametrizar, lo que permite a definir la partición como una función.  Expandir el ejemplo anterior para admitir patrones activos tiene un aspecto similar al siguiente:

[!code-fsharp[ActivePatterns](~/samples/snippets/fsharp/tour.fs#L764-L786)]

## <a name="optional-types"></a>Tipos opcionales

Un caso especial de tipos de Unión discriminada es el tipo de opción, que es tan útil que forma parte de la biblioteca básica de F #.

[El tipo de opción](./language-reference/options.md) es un tipo que representa uno de los dos casos: un valor o nada en absoluto.  Se usa en cualquier escenario en el que un valor pueda o no ser el resultado de una operación determinada.  Esto le obliga a tener en cuenta los dos casos, convirtiéndolo en un problema de tiempo de compilación en lugar de un problema en tiempo de ejecución.  A menudo se usan en las API donde `null` se usa para representar "Nothing" en su lugar, lo que elimina la necesidad de preocuparse por `NullReferenceException` muchas circunstancias.

[!code-fsharp[Options](~/samples/snippets/fsharp/tour.fs#L789-L814)]

## <a name="units-of-measure"></a>Unidades de medida

Una característica única del sistema de tipos de F # es la posibilidad de proporcionar contexto para literales numéricos a través de unidades de medida.

Las [unidades de medida](./language-reference/units-of-measure.md) permiten asociar un tipo numérico a una unidad, como los medidores, y hacer que las funciones realicen trabajos en unidades en lugar de literales numéricos.  Esto permite al compilador comprobar que los tipos de literales numéricos pasados tienen sentido en un contexto determinado, con lo que se eliminan los errores en tiempo de ejecución asociados a ese tipo de trabajo.

[!code-fsharp[UnitsOfMeasure](~/samples/snippets/fsharp/tour.fs#L817-L842)]

La biblioteca básica de F # define muchos tipos de unidades de SI y conversiones de unidad.  Para obtener más información, consulte el [espacio de nombres FSharp. Data. UnitSystems. Si. UnitSymbols](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-data-unitsystems-si-unitsymbols.html).

## <a name="classes-and-interfaces"></a>Clases e interfaces

F # también tiene compatibilidad total con clases de .NET, [interfaces](./language-reference/interfaces.md), [clases abstractas](./language-reference/abstract-classes.md), [herencia](./language-reference/inheritance.md), etc.

[Las clases](./language-reference/classes.md) son tipos que representan objetos .net, que pueden tener propiedades, métodos y eventos como [miembros](./language-reference/members/index.md).

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L845-L880)]

La definición de clases genéricas también es muy sencilla.

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L883-L908)]

Para implementar una interfaz, puede usar cualquier `interface ... with` Sintaxis o una [expresión de objeto](./language-reference/object-expressions.md).

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L911-L934)]

## <a name="which-types-to-use"></a>Qué tipos se van a usar

La presencia de clases, registros, uniones discriminadas y tuplas conduce a una pregunta importante: ¿Qué debería usar?  Como la mayoría de los casos, la respuesta depende de sus circunstancias.

Las tuplas son excelentes para devolver varios valores de una función y usar un agregado ad hoc de valores como un valor en sí.

Los registros son un "paso activo" de las tuplas, que tienen etiquetas con nombre y admiten miembros opcionales.  Son excelentes para una representación de datos en tránsito con un bajo nivel de ceremonia a través del programa.  Dado que tienen igualdad estructural, son fáciles de usar con la comparación.

Las uniones discriminadas tienen muchos usos, pero la ventaja principal es poder usarlas junto con la coincidencia de patrones para tener en cuenta todas las posibles "formas" que pueden tener los datos.  

Las clases son excelentes para una gran cantidad de razones, como cuando es necesario representar información y también asociar esa información a la funcionalidad.  Como regla general, cuando tiene funcionalidad que está vinculada conceptualmente a algunos datos, el uso de clases y los principios de la programación orientada a objetos es una gran ventaja.  Las clases son también el tipo de datos preferido al interoperar con C# y Visual Basic, ya que estos lenguajes usan clases para casi todo.

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha visto algunas de las características principales del lenguaje, debe estar listo para escribir los primeros programas de F #.  Consulte [Introducción](get-started/index.md) para obtener información sobre cómo configurar el entorno de desarrollo y escribir código.

Los siguientes pasos para obtener más información pueden ser el que desee, pero se recomienda la [Introducción a la programación funcional en F #](./introduction-to-functional-programming/index.md) para familiarizarse con los conceptos básicos de la programación funcional.  Serán esenciales para compilar programas eficaces en F #.

Además, consulte la [Referencia del lenguaje f #](./language-reference/index.md) para ver una colección completa de contenido conceptual en f #.
