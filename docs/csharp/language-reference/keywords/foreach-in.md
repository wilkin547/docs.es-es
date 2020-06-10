---
title: Instrucción foreach de C#
ms.date: 06/03/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 1645a246c9feee2a92c0d4e4bbeda47f0afde7d9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401893"
---
# <a name="foreach-in-c-reference"></a>foreach, in (Referencia de C#)

La instrucción `foreach` ejecuta una instrucción o un bloque de instrucciones para cada elemento en una instancia del tipo que implementa la interfaz <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. La instrucción `foreach` no se limita a esos tipos y puede aplicarse a una instancia de cualquier tipo que cumpla las siguientes condiciones:

- tiene el método público sin parámetros `GetEnumerator` cuyo tipo de valor devuelto es clase, estructura o tipo de interfaz,
- el tipo de valor devuelto del método `GetEnumerator` tiene la propiedad pública `Current` y el método público sin parámetros `MoveNext` cuyo tipo de valor devuelto es <xref:System.Boolean>.

En la mayoría de casos, `foreach` itera una expresión `IEnumerable<T>` en la que cada elemento es de tipo `T`. Pero los elementos pueden ser de cualquier tipo que tenga una conversión implícita o explícita del tipo de la propiedad `Current`. Si la propiedad `Current` devuelve `SomeType`, el tipo de los elementos puede ser uno de los siguientes:

- Cualquiera de las clases base de `SomeType`.
- Cualquiera de las interfaces implementadas por `SomeType`.

Además, si `SomeType` es una `class` o una `interface` y no tiene el estado `sealed`, el tipo de elemento puede ser uno de los siguientes:

- Cualquier tipo derivado de `SomeType`.
- Cualquier interfaz arbitraria. Se permite cualquier interfaz porque se puede usar una clase derivada de `SomeType` o que implemente este elemento para implementar cualquier interfaz.

Puede declarar la variable de iteración con cualquier tipo que coincida con las reglas anteriores. Si la conversión de `SomeType` al tipo de la variable de iteración requiere una conversión explícita, dicha operación puede producir una excepción <xref:System.InvalidCastException> al producirse un error de conversión.

A partir de C# 7.3, si la propiedad `Current` del enumerador devuelve un [valor devuelto de referencia](ref.md#reference-return-values) (`ref T` donde `T` es el tipo del elemento de colección), se puede declarar la variable de iteración con el modificador `ref` o `ref readonly`.

A partir de C# 8.0, el operador `await` se puede aplicar a la instrucción `foreach` cuando el tipo de colección implemente la interfaz <xref:System.Collections.Generic.IAsyncEnumerable%601>. Cada iteración del bucle se puede suspender mientras el siguiente elemento se recupera de forma asincrónica. Los elementos de secuencia se procesan de forma predeterminada en el contexto capturado. Si quiere deshabilitar la captura del contexto, use el método de extensión <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType>. Para obtener más información sobre los contextos de sincronización y la captura del contexto actual, vea el artículo sobre el [consumo del patrón asincrónico basado en tareas](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).

En cualquier punto del bloque de instrucciones `foreach`, se puede salir del bucle mediante la instrucción [break](break.md), o bien se puede ir a la siguiente iteración del bucle mediante la instrucción [continue](continue.md). También se puede salir de un bucle `foreach` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).

Si la instrucción `foreach` se aplica a `null`, se produce <xref:System.NullReferenceException>. Si la colección de origen de la instrucción `foreach` está vacía, el cuerpo del bucle `foreach` no se ejecuta y se omite.

## <a name="examples"></a>Ejemplos

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

El siguiente ejemplo muestra el uso de la instrucción `foreach` con una instancia del tipo <xref:System.Collections.Generic.List%601> que implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601>:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

El siguiente ejemplo utiliza la instrucción `foreach` con una instancia del tipo <xref:System.Span%601?displayProperty=nameWithType>, que no implementa ninguna interfaz:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

En el ejemplo siguiente se usa una variable de iteración `ref` para establecer el valor de cada elemento de una matriz stackalloc. La versión `ref readonly` recorre en iteración la colección para imprimir todos los valores. En la declaración de `readonly`, se usa una declaración de variable local implícita. Las declaraciones de variables implícitas se pueden usar con las declaraciones `ref` o `ref readonly`, al igual que las declaraciones de variables con tipo explícito.

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

En el siguiente ejemplo se usa `await foreach` para iterar por una colección que genera cada elemento de forma asincrónica:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach"  :::

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea la sección sobre la [instrucción foreach](~/_csharplang/spec/statements.md#the-foreach-statement) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Utilizar foreach con matrices](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [for (Instrucción)](for.md)
