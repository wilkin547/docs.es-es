---
title: Tuplas
description: 'Obtenga información sobre la tupla de F #, una agrupación de valores sin nombre pero ordenados, posiblemente de tipos diferentes.'
ms.date: 05/16/2016
ms.openlocfilehash: 5d26fd5d7ec5b4939a895a6d2a6a0d7fc6c6c733
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173294"
---
# <a name="tuples"></a>Tuplas

Una *tupla* es una agrupación de valores sin nombre pero ordenados, posiblemente de tipos diferentes.  Las tuplas pueden ser tipos de referencia o Structs.

## <a name="syntax"></a>Sintaxis

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a>Observaciones

Cada *elemento* de la sintaxis anterior puede ser cualquier expresión de F # válida.

## <a name="examples"></a>Ejemplos

Entre los ejemplos de tuplas se incluyen pares, tripas, etc., del mismo tipo o de tipos diferentes. En el código siguiente se muestran algunos ejemplos.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a>Obtener valores individuales

Puede usar la coincidencia de patrones para obtener acceso y asignar nombres para los elementos de tupla, como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

También puede deconstruir una tupla a través de la coincidencia de patrones fuera de una `match` expresión a través del `let` enlace:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

O bien, puede buscar coincidencias en tuplas como entradas en funciones:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

Si solo necesita un elemento de la tupla, se puede usar el carácter comodín (el carácter de subrayado) para evitar la creación de un nuevo nombre para un valor que no necesite.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

Copiar elementos de una tupla de referencia en una tupla de struct también es simple:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

Las funciones `fst` y `snd` (solo tuplas de referencia) devuelven el primer y el segundo elemento de una tupla, respectivamente.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

No hay ninguna función integrada que devuelva el tercer elemento de un triple, pero se puede escribir fácilmente como se indica a continuación.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

Por lo general, es mejor usar la coincidencia de patrones para tener acceso a elementos de tupla individuales.

## <a name="using-tuples"></a>Usar tuplas

Las tuplas proporcionan una manera cómoda de devolver varios valores de una función, tal como se muestra en el ejemplo siguiente. Este ejemplo realiza una división de enteros y devuelve el resultado redondeado de la operación como un primer miembro de un par de tupla y el resto como un segundo miembro del par.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

Las tuplas también se pueden usar como argumentos de función cuando se desea evitar el currificación implícito de los argumentos de función que está implícito en la sintaxis de función habitual.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

La sintaxis habitual para definir la función `let sum a b = a + b` permite definir una función que es la aplicación parcial del primer argumento de la función, tal y como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

El uso de una tupla como parámetro deshabilita currificación. Para obtener más información, vea "aplicación parcial de argumentos" en [funciones](./functions/index.md).

## <a name="names-of-tuple-types"></a>Nombres de tipos de tupla

Cuando se escribe el nombre de un tipo que es una tupla, se usa el `*` símbolo para separar los elementos. Para una tupla que consta de un, `int` un `float` y un `string` , como `(10, 10.0, "ten")` , el tipo se escribiría como se indica a continuación.

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a>Interoperación con tuplas de C#

C# 7,0 presentó tuplas en el lenguaje.  Las tuplas en C# son estructuras y son equivalentes a las tuplas de struct en F #.  Si necesita interoperar con C#, debe utilizar tuplas de struct.

Esto es fácil de hacer.  Por ejemplo, Imagine que tiene que pasar una tupla a una clase de C# y luego consumir su resultado, que también es una tupla:

```csharp
namespace CSharpTupleInterop
{
    public static class Example
    {
        public static (int, int) AddOneToXAndY((int x, int y) a) =>
            (a.x + 1, a.y + 1);
    }
}
```

En el código de F #, puede pasar una tupla de struct como parámetro y consumir el resultado como una tupla de estructura.

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a>Convertir entre tuplas de referencia y tuplas de struct

Dado que las tuplas de referencia y las tuplas de struct tienen una representación subyacente completamente diferente, no se pueden convertir implícitamente.  Es decir, el código como el siguiente no se compilará:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

Debe crear patrones de coincidencia en una tupla y construir la otra con las partes constituyentes.  Por ejemplo:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a>Forma compilada de tuplas de referencia

En esta sección se explica la forma de las tuplas cuando se compilan.  Esta información no es necesaria para leer a menos que tenga como destino .NET Framework 3,5 o inferior.

Las tuplas se compilan en objetos de uno de varios tipos genéricos, todos los nombres `System.Tuple` , que están sobrecargados en la aridad o el número de parámetros de tipo. Los tipos de tupla aparecen en este formulario cuando se ven desde otro lenguaje, como C# o Visual Basic, o cuando se usa una herramienta que no es consciente de las construcciones de F #. Los `Tuple` tipos se introdujeron en .NET Framework 4. Si el destino es una versión anterior del .NET Framework, el compilador usa versiones de [System. Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) de la versión 2,0 de la biblioteca básica de F #. Los tipos de esta biblioteca solo se usan para las aplicaciones destinadas a las versiones 2,0, 3,0 y 3,5 del .NET Framework. El reenvío de tipos se usa para garantizar la compatibilidad binaria entre .NET Framework 2,0 y .NET Framework 4 componentes de F #.

### <a name="compiled-form-of-struct-tuples"></a>Forma compilada de tuplas de struct

Las tuplas de estructura (por ejemplo, `struct (x, y)` ), son fundamentalmente distintas de las tuplas de referencia.  Se compilan en el <xref:System.ValueTuple> tipo, sobrecargado por aridad o el número de parámetros de tipo.  Son equivalentes a las tuplas de [C# 7,0](../../csharp/language-reference/builtin-types/value-tuples.md) y [Visual Basic las tuplas 2017](../../visual-basic/programming-guide/language-features/data-types/tuples.md), e interoperan bidireccionalmente.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Tipos en F#](fsharp-types.md)
