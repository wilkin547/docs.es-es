---
description: foreach, in (Referencia de C#)
title: Instrucción foreach de C#
ms.date: 09/18/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: ea8a6f86595348a32b707caf9782f84147fefc87
ms.sourcegitcommit: 43ed174f085840ca18a791dc89fe833174da766d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90828895"
---
# <a name="foreach-in-c-reference"></a>foreach, in (Referencia de C#)

La instrucción `foreach` ejecuta una instrucción o un bloque de instrucciones para cada elemento de una instancia del tipo que implementa la interfaz <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>, como se muestra en el siguiente ejemplo:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

La instrucción `foreach` no está limitada a esos tipos. Puede usarla con una instancia de cualquier tipo que cumpla las condiciones siguientes:

- Un tipo tiene el método público `GetEnumerator` sin parámetros cuyo tipo de valor devuelto es una clase, una estructura o un tipo de interfaz. A partir de C# 9.0, el método `GetEnumerator` puede ser el [método de extensión](../../programming-guide/classes-and-structs/extension-methods.md) de un tipo.
- El tipo de valor devuelto del método `GetEnumerator` tiene la propiedad pública `Current` y el método público `MoveNext` sin parámetros, cuyo tipo de valor devuelto es <xref:System.Boolean>.

En el siguiente ejemplo se usa la instrucción `foreach` con una instancia del tipo <xref:System.Span%601?displayProperty=nameWithType>, que no implementa ninguna interfaz:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

A partir de C# 7.3, si la propiedad `Current` del enumerador devuelve un [valor devuelto de referencia](ref.md#reference-return-values) (`ref T` donde `T` es el tipo de un elemento de colección), se puede declarar una variable de iteración con el modificador `ref` o `ref readonly`, como se muestra en el siguiente ejemplo:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

A partir de C# 8.0, puede usar la instrucción `await foreach` para usar una secuencia de datos asincrónica, es decir, el tipo de colección que implementa la interfaz <xref:System.Collections.Generic.IAsyncEnumerable%601>. Cada iteración del bucle se puede suspender mientras el siguiente elemento se recupera de forma asincrónica. En el ejemplo siguiente se muestra cómo usar la instrucción `await foreach`:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach" :::

Los elementos de secuencia se procesan de forma predeterminada en el contexto capturado. Si quiere deshabilitar la captura del contexto, use el método de extensión <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType>. Para obtener más información sobre los contextos de sincronización y la captura del contexto actual, vea [Utilizar el modelo asincrónico basado en tareas](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md). Para obtener más información sobre secuencias asincrónicas, vea la sección [Secuencias asincrónicas](../../whats-new/csharp-8.md#asynchronous-streams) del artículo [Novedades de C# 8.0](../../whats-new/csharp-8.md).

En cualquier punto del bloque de instrucciones `foreach`, se puede salir del bucle mediante la instrucción [break](break.md), o bien se puede ir a la siguiente iteración del bucle mediante la instrucción [continue](continue.md). También se puede salir de un bucle `foreach` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).

Si la instrucción `foreach` se aplica a `null`, se produce <xref:System.NullReferenceException>. Si la colección de origen de la instrucción `foreach` está vacía, el cuerpo del bucle `foreach` no se ejecuta y se omite.

## <a name="type-of-an-iteration-variable"></a>Tipo de una variable de iteración

Puede usar la palabra clave `var` para permitir que el compilador infiera el tipo de una variable de iteración de la instrucción `foreach`, como se muestra en el código siguiente:

```csharp
foreach (var item in collection) { }
```

También puede especificar de forma explícita el tipo de una variable de iteración, como se muestra en el código siguiente:

```csharp
IEnumerable<T> collection = new T[5];
foreach (V item in collection) { }
```

En el formulario anterior, el tipo `T` de un elemento de colección se debe poder convertir de forma implícita o explícita en el tipo `V` de una variable de iteración. Si se produce un error en una conversión explícita de `T` en `V` en tiempo de ejecución, la instrucción `foreach` produce <xref:System.InvalidCastException>. Por ejemplo, si `T` es un tipo de clase no sellada, `V` puede ser cualquier tipo de interfaz, incluso uno que `T` no implemente. En tiempo de ejecución, el tipo de un elemento de colección puede ser el que deriva de `T` y realmente implementa `V`. Si ese no es el caso, se produce <xref:System.InvalidCastException>.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea la sección sobre la [instrucción foreach](~/_csharplang/spec/statements.md#the-foreach-statement) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

Para obtener más información sobre de las características agregadas en C# 8.0 y versiones posteriores, vea las siguientes notas de propuesta de características:

- [Flujos asincrónicos (C# 8.0)](~/_csharplang/proposals/csharp-8.0/async-streams.md)
- [Compatibilidad con extensiones `GetEnumerator` para bucles `foreach` (C# 9.0)](~/_csharplang/proposals/csharp-9.0/extension-getenumerator.md)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Palabras clave de C#](index.md)
- [Utilizar foreach con matrices](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [for (Instrucción)](for.md)
