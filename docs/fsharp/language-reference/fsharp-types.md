---
title: Tipos en F#
description: Obtenga información sobre los tipos que se usan en F# y cómo F# se denominado y se describen los tipos.
ms.date: 05/16/2016
ms.openlocfilehash: b48376c80b48df210bf7bc699a769d40fec60864
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934646"
---
# <a name="f-types"></a>Tipos en F#

En este tema se describe los tipos que se usan en F# y cómo F# se denominado y se describen los tipos.

## <a name="summary-of-f-types"></a>Resumen de F# tipos
Algunos tipos se consideran *tipos primitivos*, como el tipo Boolean `bool` y tipos enteros y de punto flotante de diversos tamaños, que incluyen tipos para bytes y caracteres. Estos tipos se describen en [tipos primitivos](primitive-types.md).

Otros tipos que están integrados en el lenguaje incluyen las tuplas, listas, matrices, secuencias, registros y uniones discriminadas. Si tiene experiencia con otros lenguajes .NET y aprendizaje F#, debería leer los temas para cada uno de estos tipos. Vínculos para obtener más información acerca de estos tipos se incluyen en el [temas relacionados](https://msdn.microsoft.com/library/#rel) sección de este tema. Estos F#-tipos específicos admiten estilos de programación que son comunes a los lenguajes de programación funcionales. Muchos de estos tipos tienen módulos asociados en el F# biblioteca que admiten operaciones comunes en estos tipos.

El tipo de una función incluye información acerca de los tipos de parámetros y tipo de valor devuelto.

.NET Framework es el origen de los tipos de objetos, tipos de interfaz, tipos de delegado y otros usuarios. Puede definir sus propios tipos de objeto se puede hacer en cualquier otro lenguaje. NET.

Además, F# código puede definir los alias, que se denominan *abreviaturas de tipo*, que son nombres alternativos para los tipos. Puede usar las abreviaturas de tipo cuando el tipo podría cambiar en el futuro y desea evitar cambiar el código que depende del tipo. O bien, podría utilizar una abreviatura del tipo como un nombre descriptivo para un tipo que puede hacer que código más fácil de leer y comprender.

F#Proporciona tipos de colección útil que están diseñados con la programación funcional en mente. Estos tipos de colección le ayuda a escribir código que sea más funcional en estilo. Para obtener más información, consulte [ F# tipos de colección](fsharp-collection-types.md).

## <a name="syntax-for-types"></a>Sintaxis de tipos
En F# código, a menudo tendrá que escribir los nombres de tipos. Cada tipo tiene un formulario sintáctico y usar estas formas en las anotaciones de tipo, declaraciones de métodos abstractos, declaraciones de delegados, firmas y otras construcciones sintácticas. Siempre que se declara una nueva construcción de programa en el intérprete, el intérprete imprime el nombre de la construcción y la sintaxis para su tipo. Esta sintaxis puede ser simplemente un identificador para un tipo definido por el usuario o un identificador integrado tal como para `int` o `string`, pero para los tipos más complejos, la sintaxis es más compleja.

En la tabla siguiente se muestra los aspectos de la sintaxis de tipo para F# tipos.

|Tipo|Sintaxis de tipo|Ejemplos|
|----|-----------|--------|
|tipo primitivo|*type-name*|`int`<br /><br />`float`<br /><br />`string`|
|tipo de agregado (clase, estructura, unión, registro, enumeración etc.)|*type-name*|`System.DateTime`<br /><br />`Color`|
|abreviatura de tipo|*type-abbreviation-name*|`bigint`|
|nombre completo del tipo|*namespaces.type-name*<br /><br />o<br /><br />*modules.type-name*<br /><br />o<br /><br />*namespaces.modules.type-name*|`System.IO.StreamWriter`|
|array|*type-name*[] or<br /><br />*nombre de tipo* matriz|`int[]`<br /><br />`array<int>`<br /><br />`int array`|
|matriz bidimensional|*type-name*[,]|`int[,]`<br /><br />`float[,]`|
|matriz tridimensional|*type-name*[,,]|`float[,,]`|
|tuple|*type-name1* &#42; *type-name2* ...|Por ejemplo, `(1,'b',3)` tiene el tipo `int * char * int`|
|tipo genérico|*type-parameter* *generic-type-name*<br /><br />o<br /><br />*generic-type-name*&lt;*type-parameter-list*&gt;|`'a list`<br /><br />`list<'a>`<br /><br />`Dictionary<'key, 'value>`|
|(un tipo genérico que tiene un argumento de tipo específico proporcionado) del tipo construido|*type-argument* *generic-type-name*<br /><br />o<br /><br />*generic-type-name*&lt;*type-argument-list*&gt;|`int option`<br /><br />`string list`<br /><br />`int ref`<br /><br />`option<int>`<br /><br />`list<string>`<br /><br />`ref<int>`<br /><br />`Dictionary<int, string>`|
|tipo de función que tiene un único parámetro|*parameter-type1* -&gt; *return-type*|Una función que toma un `int` y devuelve un `string` tiene un tipo `int -> string`|
|tipo de función que tiene varios parámetros|*parameter-type1* -&gt; *parameter-type2* -&gt; ... -&gt; *return-type*|Una función que toma un `int` y un `float` y devuelve un `string` tiene un tipo `int -> float -> string`|
|función de orden superior como un parámetro|(*function-type*)|`List.map` tiene un tipo `('a -> 'b) -> 'a list -> 'b list`|
|delegado|delegado de *tipo de función*|`delegate of unit -> int`|
|tipo flexible|#*type-name*|`#System.Windows.Forms.Control`<br /><br />`#seq<int>`|

## <a name="related-topics"></a>Temas relacionados

|Tema|Descripción|
|-----|-----------|
|[Tipos primitivos](primitive-types.md)|Describe los tipos simples integrados como tipos enteros, el tipo booleano y tipos de caracteres.|
|[Tipo unit](unit-type.md)|Describe el `unit` tipo, un tipo que tiene un valor y que se indica mediante (); equivalente a `void` en C# y `Nothing` en Visual Basic.|
|[Tuplas](tuples.md)|Describe el tipo de tupla, que consta de los valores asociados de cualquier tipo que se agrupan en pares, triples, cuartetos y así sucesivamente.|
|[Opciones](options.md)|Describe el tipo de opción, que puede tener un valor o estar vacío.|
|[Listas](lists.md)|Describe las listas, que son una serie ordenada e inmutable de elementos del mismo tipo.|
|[Matrices](arrays.md)|Describe las matrices, que son conjuntos ordenadas de los elementos del mismo tipo mutables que ocupan un bloque de memoria contiguo y son de tamaño fijo.|
|[Secuencias](sequences.md)|Describe el tipo de secuencia, que representa una serie lógica de valores. los valores individuales se calculan únicamente cuando sea necesario.|
|[Registros](records.md)|Describe el tipo de registro, un agregado pequeño de valores con nombre.|
|[Uniones discriminadas](discriminated-unions.md)|Describe el tipo de unión discriminada, un tipo cuyos valores pueden ser cualquiera de un conjunto de tipos posibles.|
|[Funciones](functions/index.md)|Describe los valores de función.|
|[Clases](classes.md)|Describe el tipo de clase, un tipo de objeto que corresponde a un tipo de referencia. NET. Tipos de clase pueden contener miembros, propiedades, interfaces implementadas y un tipo base.|
|[Estructuras](structures.md)|Describe el `struct` tipo, un tipo de objeto que corresponde a un tipo de valor. NET. El `struct` tipo normalmente representa un agregado de datos pequeño.|
|[Interfaces](interfaces.md)|Describe los tipos de interfaz, que son tipos que representan un conjunto de miembros que proporcionan cierta funcionalidad, pero que no contienen ningún dato. Un tipo de interfaz debe implementarse mediante un tipo de objeto para ser útil.|
|[Delegados](delegates.md)|Describe el tipo de delegado, que representa una función como un objeto.|
|[Enumeraciones](enumerations.md)|Describe los tipos de enumeración, cuyos valores pertenecen a un conjunto de valores con nombre.|
|[Atributos](attributes.md)|Describe los atributos, que se usan para especificar los metadatos de otro tipo.|
|[Tipos de excepción](exception-handling/exception-types.md)|Describe las excepciones, que especifican la información de error.|
