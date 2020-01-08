---
title: Tipos
description: Obtenga información sobre los tipos que se usan F# en y F# cómo se denominan y describen los tipos.
ms.date: 05/16/2016
ms.openlocfilehash: 70d79525318c8d2eb0711d6a1b50be1ac0cf0226
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348217"
---
# <a name="f-types"></a>Tipos en F#

En este tema se describen los tipos que se F# usan en F# y cómo se denominan y describen los tipos.

## <a name="summary-of-f-types"></a>Resumen de F# tipos

Algunos tipos se consideran *tipos primitivos*, como el tipo booleano `bool` y los tipos enteros y de punto flotante de varios tamaños, entre los que se incluyen los tipos de bytes y caracteres. Estos tipos se describen en [tipos primitivos](basic-types.md).

Otros tipos que se integran en el lenguaje incluyen tuplas, listas, matrices, secuencias, registros y uniones discriminadas. Si tiene experiencia con otros lenguajes de .NET y está F#aprendiendo, debe leer los temas de cada uno de estos tipos. En la sección [temas relacionados](https://msdn.microsoft.com/library/#rel) de este tema se incluyen vínculos a más información sobre estos tipos. Estos F#tipos específicos de son compatibles con los estilos de programación que son comunes a los lenguajes de programación funcionales. Muchos de estos tipos tienen módulos asociados en la F# biblioteca que admiten operaciones comunes en estos tipos.

El tipo de una función incluye información sobre los tipos de parámetro y el tipo de valor devuelto.

La .NET Framework es el origen de los tipos de objeto, los tipos de interfaz, los tipos de delegado y otros. Puede definir sus propios tipos de objeto igual que en cualquier otro lenguaje .NET.

Además, F# el código puede definir alias, que son *abreviaturas de tipo*con nombre, que son nombres alternativos para los tipos. Puede usar las abreviaturas de tipo cuando el tipo cambie en el futuro y desee evitar cambiar el código que depende del tipo. O bien, puede usar una abreviatura de tipo como nombre descriptivo para un tipo que pueda facilitar la lectura y comprensión del código.

F#proporciona tipos de colección útiles que están diseñados pensando en la programación funcional. El uso de estos tipos de colección le ayuda a escribir código que es más funcional en estilo. Para obtener más información, vea [ F# tipos de colección](fsharp-collection-types.md).

## <a name="syntax-for-types"></a>Sintaxis para tipos

En F# el código, a menudo tiene que escribir los nombres de los tipos. Cada tipo tiene una forma sintáctica y estas formas sintácticas se utilizan en anotaciones de tipo, declaraciones de método abstractas, declaraciones de delegado, firmas y otras construcciones. Siempre que declare una nueva construcción de programa en el intérprete, el intérprete imprime el nombre de la construcción y la sintaxis de su tipo. Esta sintaxis puede ser simplemente un identificador de un tipo definido por el usuario o un identificador integrado como para `int` o `string`, pero para tipos más complejos, la sintaxis es más compleja.

En la tabla siguiente se muestran los aspectos de la F# sintaxis de tipos para los tipos.

|Tipo de|Sintaxis de tipos|Ejemplos|
|----|-----------|--------|
|tipo primitivo|*type-name*|`int`<br /><br />`float`<br /><br />`string`|
|tipo de agregado (clase, estructura, Unión, registro, enumeración, etc.)|*type-name*|`System.DateTime`<br /><br />`Color`|
|abreviatura de tipo|*type-abbreviation-name*|`bigint`|
|tipo completo|*namespaces.type-name*<br /><br />o<br /><br />*modules.type-name*<br /><br />o<br /><br />*namespaces.modules.type-name*|`System.IO.StreamWriter`|
|matriz|*nombre de tipo*[] o<br /><br />matriz *de nombres de tipo*|`int[]`<br /><br />`array<int>`<br /><br />`int array`|
|matriz bidimensional|*type-name*[,]|`int[,]`<br /><br />`float[,]`|
|matriz tridimensional|*nombre de tipo*[,,]|`float[,,]`|
|tuple|*Type-nombre1* &#42; *Type-nombre2* ...|Por ejemplo, `(1,'b',3)` tiene el tipo `int * char * int`|
|tipo genérico|*type-parameter* *generic-type-name*<br /><br />o<br /><br />*generic-type-name*&lt;*type-parameter-list*&gt;|`'a list`<br /><br />`list<'a>`<br /><br />`Dictionary<'key, 'value>`|
|tipo construido (un tipo genérico que tiene un argumento de tipo específico proporcionado)|*type-argument* *generic-type-name*<br /><br />o<br /><br />*generic-type-name*&lt;*type-argument-list*&gt;|`int option`<br /><br />`string list`<br /><br />`int ref`<br /><br />`option<int>`<br /><br />`list<string>`<br /><br />`ref<int>`<br /><br />`Dictionary<int, string>`|
|tipo de función que tiene un parámetro único|*parameter-type1* -&gt; *return-type*|Función que toma un `int` y devuelve un `string` tiene el tipo `int -> string`|
|tipo de función que tiene varios parámetros|*parámetro-type1* -&gt; *parámetro-tipo2* -&gt;...-&gt; *tipo de valor devuelto*|Una función que toma un `int` y un `float` y devuelve una `string` tiene el tipo `int -> float -> string`|
|función de orden superior como parámetro|(*tipo de función*)|`List.map` tiene el tipo `('a -> 'b) -> 'a list -> 'b list`|
|delegate|Delegado de *tipo de función*|`delegate of unit -> int`|
|tipo flexible|*nombre del tipo de* #|`#System.Windows.Forms.Control`<br /><br />`#seq<int>`|

## <a name="related-topics"></a>Temas relacionados

|Tema|Descripción|
|-----|-----------|
|[Tipos primitivos](basic-types.md)|Describe los tipos simples integrados, como los tipos enteros, el tipo booleano y los tipos de caracteres.|
|[Tipo unit](unit-type.md)|Describe el tipo de `unit`, un tipo que tiene un valor y que se indica mediante (); equivalente a `void` en C# y `Nothing` en Visual Basic.|
|[Tuplas](tuples.md)|Describe el tipo de tupla, un tipo que consta de valores asociados de cualquier tipo agrupados en pares, tripas, cuadruplican, etc.|
|[Opciones](options.md)|Describe el tipo de opción, un tipo que puede tener un valor o estar vacío.|
|[Listas](lists.md)|Describe las listas, que son una serie ordenada e inmutable de elementos del mismo tipo.|
|[Matrices](arrays.md)|Describe las matrices, que son conjuntos ordenados de elementos mutables del mismo tipo que ocupan un bloque de memoria contiguo y tienen un tamaño fijo.|
|[Secuencias](sequences.md)|Describe el tipo de secuencia, que representa una serie lógica de valores; los valores individuales se calculan solo según sea necesario.|
|[Registros](records.md)|Describe el tipo de registro, un agregado pequeño de valores con nombre.|
|[Uniones discriminadas](discriminated-unions.md)|Describe el tipo de Unión discriminada, un tipo cuyos valores pueden ser cualquiera de un conjunto de tipos posibles.|
|[Funciones](./functions/index.md)|Describe los valores de función.|
|[Clases](classes.md)|Describe el tipo de clase, un tipo de objeto que corresponde a un tipo de referencia de .NET. Los tipos de clase pueden contener miembros, propiedades, interfaces implementadas y un tipo base.|
|[Estructuras](structures.md)|Describe el tipo de `struct`, un tipo de objeto que corresponde a un tipo de valor de .NET. Normalmente, el tipo de `struct` representa un agregado pequeño de datos.|
|[Interfaces](interfaces.md)|Describe los tipos de interfaz, que son tipos que representan un conjunto de miembros que proporcionan ciertas funciones, pero que no contienen datos. Un tipo de interfaz debe ser implementado por un tipo de objeto para que sea útil.|
|[Delegados](delegates.md)|Describe el tipo de delegado, que representa una función como un objeto.|
|[Enumeraciones](enumerations.md)|Describe los tipos de enumeración, cuyos valores pertenecen a un conjunto de valores con nombre.|
|[Atributos](attributes.md)|Describe los atributos, que se usan para especificar los metadatos de otro tipo.|
|[Tipos de excepción](./exception-handling/exception-types.md)|Describe las excepciones, que especifican la información de error.|
