---
title: using (Instrucción, Referencia de C#)
ms.date: 04/07/2020
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: a237a90b4782e0460857c3d5d887771bcc8ccaaf
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989186"
---
# <a name="using-statement-c-reference"></a>using (Instrucción, Referencia de C#)

Ofrece una sintaxis adecuada que garantiza el uso correcto de objetos <xref:System.IDisposable>. A partir de C# 8.0, la instrucción `using` garantiza el uso correcto de los objetos <xref:System.IAsyncDisposable>.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo usar la instrucción `using`.

:::code language="csharp" source="snippets/usings.cs" id="SnippetFirstExample":::

A partir de C# 8.0, puede usar la siguiente sintaxis alternativa para la instrucción `using` que no requiere llaves:

:::code language="csharp" source="snippets/usings.cs" id="SnippetModernUsing":::

## <a name="remarks"></a>Comentarios

<xref:System.IO.File> y <xref:System.Drawing.Font> son ejemplos de tipos administrados que acceden a recursos no administrados (en este caso, identificadores de archivo y contextos de dispositivo). Hay muchos otros tipos de recursos no administrados y tipos de la biblioteca de clases que los encapsulan. Todos estos tipos deben implementar la interfaz <xref:System.IDisposable> o la interfaz <xref:System.IAsyncDisposable>.

Cuando la duración de un objeto `IDisposable` se limita a un único método, debe declarar y crear instancias del mismo en la instrucción `using`. La instrucción `using` llama al método <xref:System.IDisposable.Dispose%2A> del objeto de forma correcta y (cuando se usa tal y como se muestra anteriormente) también hace que el propio objeto salga del ámbito en cuanto se llame a <xref:System.IDisposable.Dispose%2A>. Dentro del bloque `using`, el objeto es de solo lectura y no se puede modificar ni reasignar. Si el objeto implementa `IAsyncDisposable` en lugar de `IDisposable`, la instrucción `using` llama al objeto <xref:System.IAsyncDisposable.DisposeAsync%2A> y `awaits` al objeto <xref:System.Threading.Tasks.Task> devuelto.

La instrucción `using` asegura que se llama al método <xref:System.IDisposable.Dispose%2A> (o <xref:System.IAsyncDisposable.DisposeAsync%2A>) aunque se produzca una excepción en el bloque `using`. Puede lograr el mismo resultado colocando el objeto dentro de un bloque `try` y llamando luego a <xref:System.IDisposable.Dispose%2A> (o <xref:System.IAsyncDisposable.DisposeAsync%2A>) en un bloque `finally`; de hecho, es así cómo el compilador traduce la instrucción `using`. El ejemplo de código anterior se extiende al siguiente código en tiempo de compilación (tenga en cuenta las llaves adicionales para crear el ámbito limitado del objeto):

:::code language="csharp" source="snippets/usings.cs" id="SnippetTryFinallyExample":::

La nueva sintaxis de la instrucción `using` se traduce en un código similar. Se abre el bloque `try` en el que se declara la variable. El bloque `finally` se agrega al cierre del bloque de inclusión, normalmente, al final de un método.

Consulte el artículo sobre [try-finally](try-finally.md) para obtener más información sobre la instrucción `try`-`finally`.

Se pueden declarar varias instancias de un tipo en una sola instrucción `using`, tal y como se muestra en el ejemplo siguiente. Tenga en cuenta que no se pueden usar variables con tipo implícito (`var`) cuando se declaran varias variables en una sola instrucción:

:::code language="csharp" source="snippets/usings.cs" id="SnippetDeclareMultipleVariables":::

También puede combinar varias declaraciones del mismo tipo con la nueva sintaxis introducida con C# 8, tal y como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/usings.cs" id="SnippetModernMultipleVariables":::

Puede crear una instancia del objeto de recurso y luego pasar la variable a la instrucción `using`, pero esto no es un procedimiento recomendado. En este caso, después de que el control abandone el bloque `using` el objeto permanece en el ámbito, pero probablemente ya no tenga acceso a sus recursos no administrados. En otras palabras, ya no se inicializa totalmente. Si intenta usar el objeto fuera del bloque `using`, corre el riesgo de iniciar una excepción. Por este motivo, es mejor crear una instancia del objeto en la instrucción `using` y limitar su ámbito al bloque `using`.

:::code language="csharp" source="snippets/usings.cs" id="SnippetDeclareBeforeUsing":::

Para obtener más información sobre cómo eliminar objetos `IDisposable`, vea [Uso de objetos que implementan IDisposable](../../../standard/garbage-collection/using-objects.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea el apartado [Instrucción using](~/_csharplang/spec/statements.md#the-using-statement) en la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [using (directiva)](using-directive.md)
- [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md)
- [Uso de objetos que implementan IDisposable](../../../standard/garbage-collection/using-objects.md)
- [IDisposable interface](xref:System.IDisposable) (Interfaz IDisposable)
- [Instrucción using en C# 8.0](~/_csharplang/proposals/csharp-8.0/using.md)
