---
title: Tipos en F#
description: 'Obtenga información acerca de los tipos que se usan en F # y cómo se denomina y se describen los tipos de F #.'
ms.date: 05/16/2016
ms.openlocfilehash: bdbb89dc751970ac31fe102df009f0bff6388e52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565594"
---
# <a name="f-types"></a>Tipos en F#

En este tema se describe los tipos que se usan en F # y cómo se denomina y se describen los tipos de F #.


## <a name="summary-of-f-types"></a>Resumen de tipos de F #
Algunos tipos se consideran *tipos primitivos*, como el tipo booleano `bool` y los tipos de enteros y de punto flotante de diversos tamaños, que incluyen tipos para bytes y caracteres. Estos tipos se describen en [tipos primitivos](primitive-types.md).

Otros tipos que están integradas en el lenguaje incluyen tuplas, listas, matrices, secuencias, los registros y uniones discriminadas. Si tiene experiencia con otros lenguajes .NET y está aprendiendo F #, lea los temas para cada uno de estos tipos. Vínculos para obtener más información acerca de estos tipos se incluyen en el [temas relacionados](https://msdn.microsoft.com/library/#rel) sección de este tema. Estos F #-determinados tipos admiten estilos de programación que son comunes a los lenguajes de programación funcionales. Muchos de estos tipos tienen módulos asociados en la biblioteca de F # que admiten operaciones comunes en estos tipos.

El tipo de una función incluye información sobre los tipos de parámetros y tipo de valor devuelto.

.NET Framework es el origen de los tipos de objeto, tipos de interfaz, tipos de delegado y otros usuarios. Puede definir sus propios tipos de objeto igual que lo haría en cualquier otro lenguaje. NET.

Además, código de F # permite definir alias, que se denominan *abreviaturas de tipo*, que son nombres alternativos para los tipos. Puede utilizar las abreviaturas de tipo cuando el tipo se puede cambiar en el futuro y desea evitar cambiar el código que depende del tipo. O bien, puede usar una abreviatura de tipo como un nombre descriptivo para un tipo que puede realizar en más fácil de leer y comprender el código.

F # proporciona tipos de colección útil que están diseñados con la programación funcional en mente. Estos tipos de colección le ayuda a escribir código que es más funcional con el estilo. Para obtener más información, consulte [tipos de colección F #](fsharp-collection-types.md).


## <a name="syntax-for-types"></a>Sintaxis de tipos
Código de F #, a menudo deben escribir los nombres de tipos. Cada tipo tiene un formato sintáctico y usar estos formatos sintácticos en anotaciones de tipo, declaraciones de métodos abstractos, declaraciones de delegados, signaturas y otras construcciones. Cada vez que se declara una nueva construcción de programa en el intérprete, el intérprete imprime el nombre de la construcción y la sintaxis de su tipo. Esta sintaxis puede ser simplemente un identificador para un tipo definido por el usuario o un identificador integrado tal como para `int` o `string`, pero para los tipos más complejos, la sintaxis es más compleja.

La siguiente tabla muestra los aspectos de la sintaxis de tipo para tipos de F #.



|Tipo|Sintaxis de tipo|Ejemplos|
|----|-----------|--------|
|tipo primitivo|*nombre de tipo*|`int`<br /><br />`float`<br /><br />`string`|
|tipo de agregado (clase, estructura, unión, registro, enum y así sucesivamente)|*nombre de tipo*|`System.DateTime`<br /><br />`Color`|
|abreviatura de tipo|*nombre de abreviatura de tipo*|`bigint`|
|nombre completo del tipo|*nombre de namespaces.Type*<br /><br />o<br /><br />*nombre de Modules.Type*<br /><br />o<br /><br />*nombre de namespaces.Modules.Type*|`System.IO.StreamWriter`|
|array|*nombre de tipo*[] o<br /><br />*nombre de tipo* matriz|`int[]`<br /><br />`array<int>`<br /><br />`int array`|
|matriz bidimensional|*nombre de tipo*[,]|`int[,]`<br /><br />`float[,]`|
|matriz tridimensional|*nombre de tipo*[,]|`float[,,]`|
|tuple|*tipo nombre1* &#42; *tipo nombre2* ...|Por ejemplo, `(1,'b',3)` tiene el tipo `int * char * int`|
|tipo genérico|*parámetro de tipo* *nombre de tipo genérico*<br /><br />o<br /><br />*nombre de tipo genérico*&lt;*lista de parámetros de tipo*&gt;|`'a list`<br /><br />`list<'a>`<br /><br />`Dictionary<'key, 'value>`|
|tipo (un tipo genérico que tiene un argumento de tipo específico proporcionado) construido|*argumento de tipo* *nombre de tipo genérico*<br /><br />o<br /><br />*nombre de tipo genérico*&lt;*lista de argumentos de tipo*&gt;|`int option`<br /><br />`string list`<br /><br />`int ref`<br /><br />`option<int>`<br /><br />`list<string>`<br /><br />`ref<int>`<br /><br />`Dictionary<int, string>`|
|tipo de función que tiene un único parámetro|*parámetro: type1*  - &gt; *tipo de valor devuelto*|Una función que toma un `int` y devuelve un `string` tiene un tipo `int -> string`|
|tipo de función que tiene varios parámetros|*parámetro: type1*  - &gt; *parámetro type2*  - &gt; ... -&gt; *tipo de valor devuelto*|Una función que toma un `int` y un `float` y devuelve un `string` tiene un tipo `int -> float -> string`|
|función de orden superior como un parámetro|(*tipo de función*)|`List.map` tiene un tipo `('a -> 'b) -> 'a list -> 'b list`|
|delegado|delegado de *tipo de función*|`delegate of unit -> int`|
|tipo flexible|#*nombre de tipo*|`#System.Windows.Forms.Control`<br /><br />`#seq<int>`|

## <a name="related-topics"></a>Temas relacionados


|Tema|Descripción|
|-----|-----------|
|[Tipos primitivos](primitive-types.md)|Describe los tipos simples integrados, como los tipos enteros, el tipo booleano y los tipos de caracteres.|
|[Tipo unit](unit-type.md)|Describe la `unit` tipo, un tipo que tiene un valor y que se indica mediante (); equivalente a `void` en C# y `Nothing` en Visual Basic.|
|[Tuplas](tuples.md)|Describe el tipo de tupla, que consta de los valores asociados de cualquier tipo, agrupados en pares, triples, cuartetos y así sucesivamente.|
|[Opciones](options.md)|Describe el tipo de opción, que puede tener un valor o estar vacío.|
|[Listas](lists.md)|Describe las listas, que son una serie ordenada e inmutable de elementos todos del mismo tipo.|
|[Matrices](arrays.md)|Describe las matrices, que son conjuntos ordenadas de elementos mutables del mismo tipo que ocupan un bloque de memoria contiguo y tienen un tamaño fijo.|
|[Secuencias](sequences.md)|Describe el tipo de secuencia, que representa una serie lógica de valores; los valores individuales se calculan únicamente cuando sea necesario.|
|[Registros](records.md)|Describe el tipo de registro, un agregado pequeño de valores con nombre.|
|[Uniones discriminadas](discriminated-unions.md)|Describe el tipo de unión discriminado, un tipo cuyos valores pueden ser cualquiera de un conjunto de posibles tipos.|
|[Funciones](functions/index.md)|Se describen los valores de función.|
|[Clases](classes.md)|Describe el tipo de clase, un tipo de objeto que se corresponde con un tipo de referencia. NET. Tipos de clase pueden contener miembros, propiedades, interfaces implementadas y un tipo base.|
|[Estructuras](structures.md)|Describe el `struct` tipo, un tipo de objeto que se corresponde con un tipo de valor. NET. El `struct` tipo normalmente representa un agregado pequeño de datos.|
|[Interfaces](interfaces.md)|Describe los tipos de interfaz, que son tipos que representan un conjunto de miembros que proporcionan cierta funcionalidad pero que no contienen ningún dato. Un tipo de interfaz debe implementarse mediante un tipo de objeto para ser útil.|
|[Delegados](delegates.md)|Describe el tipo de delegado, que representa una función como un objeto.|
|[Enumeraciones](enumerations.md)|Describe los tipos de enumeración, cuyos valores pertenecen a un conjunto de valores con nombre.|
|[Atributos](attributes.md)|Describe los atributos, que se usan para especificar los metadatos de otro tipo.|
|[Tipos de excepción](exception-handling/exception-types.md)|Describe las excepciones, que especifican información de error.|
