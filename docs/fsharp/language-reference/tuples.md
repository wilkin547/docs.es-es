---
title: Tuplas (F#)
description: 'Obtenga información acerca de la tupla de F #, una agrupación de valores sin nombre pero ordenados, posiblemente de tipos diferentes.'
ms.date: 05/16/2016
ms.openlocfilehash: d017a2ce8a6ad9b3cec8dfa2ee15b47f06d8f67c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="tuples"></a>Tuplas

A *tupla* es una agrupación de valores sin nombre pero ordenados, posiblemente de tipos diferentes.  Tuplas pueden ser tipos de referencia o structs.

## <a name="syntax"></a>Sintaxis

```fsharp
(element, ... , element)
struct(element, ... ,element )
```
## <a name="remarks"></a>Comentarios
Cada *elemento* en la sintaxis anterior puede ser cualquier expresión válida de F #.

## <a name="examples"></a>Ejemplos
Algunos ejemplos de tuplas son pares, los triples etc., de los tipos iguales o distintos. Algunos ejemplos se ilustran en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]
    
## <a name="obtaining-individual-values"></a>Obtener valores individuales
Puede usar una coincidencia de patrones para acceder y asignar nombres a elementos de tupla, tal como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

También puede anular una tupla a través de coincidencia de patrones fuera de un `match` expresión mediante `let` enlace:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

O puede definir como patrón coinciden en tuplas como entradas para funciones:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

Si necesita un único elemento de la tupla, el carácter comodín (el carácter de subrayado) puede utilizarse para evitar la creación de un nuevo nombre para un valor que no es necesario.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

Copiar elementos de una tupla de referencia en una tupla de struct también es simple:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

Las funciones `fst` y `snd` (hacer referencia solo tuplas) devuelve el primer y segundo elementos de una tupla, respectivamente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

No hay ninguna función integrada que devuelva el tercer elemento de un triple, pero se puede escribir fácilmente uno como se indica a continuación.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

Por lo general, es mejor usar la coincidencia de patrón para tener acceso a elementos de tupla individuales.

## <a name="using-tuples"></a>Uso de tuplas
Tuplas proporcionan una manera cómoda para devolver varios valores de una función, como se muestra en el ejemplo siguiente. En este ejemplo se realiza la división de enteros y devuelve el resultado redondeado de la operación como primer miembro de una tupla de dos elementos y el resto como segundo miembro del par.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

Si desea evitar la currificación implícita de los argumentos de función que está implícito en la sintaxis de función habitual tuplas también pueden utilizarse como argumentos de función.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

La sintaxis habitual para definir la función `let sum a b = a + b` le permite definir una función que es la aplicación parcial del primer argumento de la función, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

El uso de una tupla como parámetro deshabilita la currificación. Para obtener más información, vea "Aplicación parcial de argumentos" en [funciones](functions/index.md).

## <a name="names-of-tuple-types"></a>Nombres de tipos de tupla
Cuando se escribe el nombre de un tipo que es una tupla, use la `*` símbolos para separar los elementos. Para una tupla que consta de un `int`, `float`y un `string`, como `(10, 10.0, "ten")`, el tipo se escribiría como se indica a continuación.

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a>Interoperación con tuplas de C#

C# 7.0 incorporó tuplas del lenguaje.  Tuplas en C# son estructuras y son equivalentes a las tuplas de struct en F #.  Si tiene que interoperar con C#, debe usar un struct tuplas.

Esto es muy fácil de hacer.  Por ejemplo, imagine que tiene que pasar una tupla a una clase de C# y, a continuación, utilizar su resultado, que también es una tupla:

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

En el código de F #, a continuación, puede pasar una tupla de struct como parámetro y consumir el resultado como una tupla de struct.

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a>Convertir entre tuplas de referencia y las tuplas de Struct

Dado que tuplas de referencia y Struct Tuples tienen una representación subyacente completamente diferente, no son convertibles implícitamente.  Es decir, no se compilará código como el siguiente:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

Debe patrón coinciden en una tupla y crear otro con las partes constituyentes.  Por ejemplo:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a>Formato compilado de tuplas de referencia
Esta sección explica la forma de tuplas cuando se compilan.  La información aquí no es necesario leer a menos que se dirige a .NET Framework 3.5 o inferior.

Tuplas se compilan en objetos de uno de varios tipos genéricos, con todos los nombre `System.Tuple`, que están sobrecargados en la aridad o el número de parámetros de tipo. Tipos de tupla aparecen en este formulario cuando se visualizan desde otro lenguaje, como C# o Visual Basic, o cuando se usa una herramienta que no es compatible con construcciones de F #. El `Tuple` tipos se incorporaron en .NET Framework 4. Si se establece como destino una versión anterior de .NET Framework, el compilador utiliza las versiones de [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) desde la versión 2.0 de la biblioteca básica de F #. Los tipos de esta biblioteca se utilizan únicamente para aplicaciones que tienen como destino la versión 2.0, 3.0 y 3.5 versiones de .NET Framework. El reenvío de tipos se utiliza para garantizar la compatibilidad binaria entre los componentes de .NET Framework 2.0 y F # de .NET Framework 4.

### <a name="compiled-form-of-struct-tuples"></a>Formato compilado de tuplas de Struct

Tuplas de struct (por ejemplo, `struct (x, y)`), son fundamentalmente diferentes de tuplas de referencia.  Se compilan en el <xref:System.ValueTuple> tipo, sobrecargada por aridad o el número de parámetros de tipo.  Equivalen a [7.0 tuplas de C#](../../csharp/tuples.md) y [Visual Basic 2017 tuplas](../../visual-basic/programming-guide/language-features/data-types/tuples.md)e interoperen bidireccional.

## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

[Tipos en F#](fsharp-types.md)
