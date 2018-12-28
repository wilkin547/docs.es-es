---
title: Tuplas
description: Obtenga información sobre la F# tupla, una agrupación de valores sin nombre pero ordenados, posiblemente de tipos diferentes.
ms.date: 05/16/2016
ms.openlocfilehash: a1fc31d4dc97c0921545e53b91dcde0547002006
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611053"
---
# <a name="tuples"></a>Tuplas

Un *tupla* es una agrupación de valores sin nombre pero ordenados, posiblemente de tipos diferentes.  Tuplas pueden ser tipos de referencia o structs.

## <a name="syntax"></a>Sintaxis

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a>Comentarios

Cada *elemento* en la sintaxis anterior puede ser cualquier tipo válido F# expresión.

## <a name="examples"></a>Ejemplos

Algunos ejemplos de tuplas son pares, triples etc., de los tipos de la mismos u otro. En el código siguiente se incluyen algunos ejemplos.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a>Obtener valores individuales

Puede usar una coincidencia de patrones para acceder y asignar nombres a los elementos de tupla, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

También puede deconstruir una tupla a través de coincidencia de patrones fuera de un `match` expresión mediante `let` enlace:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

O puede definir como patrón coinciden en tuplas como entradas para funciones:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

Si necesita solo un elemento de la tupla, el carácter comodín (el carácter de subrayado) puede utilizarse para evitar la creación de un nuevo nombre para un valor que no es necesario.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

Copiar elementos de una tupla de referencia en una tupla de struct también es sencillo:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

Las funciones `fst` y `snd` (tuplas solo de referencia) devuelven el primer y segundo elementos de una tupla, respectivamente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

No hay ninguna función integrada que devuelve el tercer elemento de un triple, pero puede escribir fácilmente uno como se indica a continuación.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

Por lo general, es mejor usar la coincidencia de patrones para tener acceso a los elementos de tupla individuales.

## <a name="using-tuples"></a>Uso de tuplas

Las tuplas ofrecen una manera cómoda de devolver varios valores de una función, tal como se muestra en el ejemplo siguiente. En este ejemplo se realiza la división de enteros y devuelve el resultado redondeado de la operación como primer miembro de un par de tupla y el resto como segundo miembro del par.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

Las tuplas también se usan como argumentos de función cuando desea evitar la currificación implícita de los argumentos de función que está implícito en la sintaxis de la función habitual.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

La sintaxis habitual para definir la función `let sum a b = a + b` le permite definir una función de la aplicación parcial del primer argumento de la función, tal como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

Uso de una tupla como parámetro deshabilita la currificación. Para obtener más información, vea "Aplicación parcial de argumentos" en [funciones](functions/index.md).

## <a name="names-of-tuple-types"></a>Nombres de tipos de tupla

Al escribir el nombre de un tipo que es una tupla, usa el `*` símbolos para separar los elementos. Una tupla que consta de un `int`, un `float`y un `string`, tales como `(10, 10.0, "ten")`, el tipo se escribiría como sigue.

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a>Interoperación con tuplas de C#

C# 7.0 ha insertado las tuplas del lenguaje.  Las tuplas en C# son structs y son equivalentes a las tuplas de struct en F#.  Si tiene que interoperar con C#, debe usar tuplas de struct.

Esto es fácil de hacer.  Por ejemplo, imagine que tiene que pasar una tupla a una clase de C# y, a continuación, consumir su resultado, que también es una tupla:

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

En su F# código, a continuación, puede pasar una tupla de estructura como parámetro y consumir el resultado como una tupla de struct.

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a>Conversión entre las tuplas de referencia y las tuplas de Struct

Dado que las tuplas de referencia y Struct Tuples tienen una representación subyacente completamente diferente, no son implícitamente convertibles.  Es decir, no se compilará el código como el siguiente:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

Debe patrón coinciden en una tupla y crear otro con las partes constituyentes.  Por ejemplo:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a>Formato compilado de tuplas de referencia

Esta sección explica la forma de tuplas, cuando se compilan.  Esta información no es necesario leer a menos que tiene como destino .NET Framework 3.5 o inferior.

Las tuplas se compilan en objetos de uno de varios tipos genéricos, todos se pueden llamar `System.Tuple`, que están sobrecargados en la aridad o el número de parámetros de tipo. Tipos de tupla aparecen en este formulario cuando se ven desde otro lenguaje, como C# o Visual Basic, o cuando se utiliza una herramienta que no es consciente de F# construye. El `Tuple` tipos se incorporaron en .NET Framework 4. Si desea usar una versión anterior de .NET Framework, el compilador usa las versiones de [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) desde la versión 2.0 de la F# biblioteca principal. Los tipos de esta biblioteca se usan solo para las aplicaciones que tienen como destino la versión 2.0, 3.0 y 3.5 versiones de .NET Framework. Reenvío de tipos se usa para garantizar la compatibilidad binaria entre .NET Framework 2.0 y .NET Framework 4 F# componentes.

### <a name="compiled-form-of-struct-tuples"></a>Formato compilado de tuplas de Struct

Las tuplas de struct (por ejemplo, `struct (x, y)`), son totalmente diferente de las tuplas de referencia.  Se compilan en el <xref:System.ValueTuple> tipo, sobrecargado por aridad o el número de parámetros de tipo.  Son equivalentes a [C# 7.0 tuplas](../../csharp/tuples.md) y [Visual Basic 2017 tuplas](../../visual-basic/programming-guide/language-features/data-types/tuples.md)e interoperar bidireccionalmente.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Tipos en F#](fsharp-types.md)