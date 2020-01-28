---
title: 'Utilizar estructuras: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
ms.openlocfilehash: 47a1da4982d22c63cb762a27313590c8ec0c5dd4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743975"
---
# <a name="using-structs-c-programming-guide"></a>Uso de estructuras (Guía de programación de C#)

El tipo `struct` resulta adecuado para representar objetos pequeños como `Point`, `Rectangle`y `Color`. Aunque es igual de válido representar un punto como un elemento [class](../../language-reference/keywords/class.md) con [Propiedades autoimplementadas](./auto-implemented-properties.md), seguramente un [struct](../../language-reference/keywords/struct.md) sea más eficaz en algunos escenarios. Por ejemplo, si declara una matriz de 1000 objetos `Point` , se asignará más memoria para hacer referencia a cada objeto y, en este caso, un struct sería menos costoso. Puesto que .NET ya contiene un objeto llamado <xref:System.Drawing.Point>, la estructura de este ejemplo se llamará `Coords` en su lugar.

[!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]

Definir un constructor sin parámetros para una estructura es un error. como también lo es inicializar un campo de instancia en el cuerpo de un struct. Los miembros de struct accesibles de forma externa solo se pueden inicializar por medio de un constructor con parámetros, del constructor sin parámetros implícito, de un [inicializador de objeto](object-and-collection-initializers.md) o bien al acceder individualmente a cada miembro una vez declarado el struct. Los miembros privados o inaccesibles por cualquier otro motivo requieren el uso únicamente de constructores.

Cuando se crea un objeto de struct con el operador [new](../../language-reference/operators/new-operator.md), el objeto se crea y se llama al constructor apropiado en función de cuál sea la [firma del constructor](constructors.md#constructor-syntax). A diferencia de las clases, se pueden crear instancias de structs sin usar el operador `new` . En tal caso, no hay ninguna llamada de constructor, con lo cual la asignación es más eficaz. Pero los campos seguirán sin asignar y el objeto no se podrá usar hasta que todos los campos se inicialicen. Esto abarca la imposibilidad de obtener o establecer valores a través de propiedades.

Si se crea una instancia de un objeto de estructura usando el constructor sin parámetros, todos los miembros se asignarán según sus [valores predeterminados](../../language-reference/builtin-types/default-values.md).

Al escribir un constructor con parámetros de una estructura, todos los miembros se deben inicializar explícitamente o, de lo contrario, uno o varios de ellos permanecerán sin asignar y la estructura no se podrá usar, lo que generará el error de compilador [CS0171](../../misc/cs0171.md).

En los structs no existe el concepto de herencia que sí hay en las clases. Así, un struct no puede heredar de otra clase o de otro struct, como tampoco puede ser la base de una clase. Pero los structs sí heredan de la clase base <xref:System.Object>. Un struct puede implementar interfaces y lo hace exactamente igual que las clases.

No se puede declarar una clase mediante la palabra clave `struct`. En C#, las clases y los structs son distintos semánticamente. Un struct es un tipo de valor, mientras que una clase es un tipo de referencia. Para obtener más información, consulte [Tipos de valor](../../language-reference/builtin-types/value-types.md) y [Tipos de referencia](../../language-reference/keywords/reference-types.md).

A menos que necesite una semántica de tipo de referencia, es probable que el sistema controle una clase pequeña más eficazmente si se declara como un struct.

## <a name="example-1"></a>Ejemplo 1

En este ejemplo se muestra la inicialización de `struct` mediante constructores sin parámetros y parametrizados.

[!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]

[!code-csharp[csProgGuideObjects#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#2)]

## <a name="example-2"></a>Ejemplo 2

En este ejemplo se muestra una característica única de los structs. Se crea un objeto Coords sin usar el operador `new`. Si reemplaza la palabra `struct` por la palabra `class`, el programa no se compilará.

[!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]

[!code-csharp[csProgGuideObjects#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#3)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](index.md)
- [Structs](structs.md)
