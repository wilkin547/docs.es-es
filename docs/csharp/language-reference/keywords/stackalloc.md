---
title: 'Palabra clave stackalloc: Referencia de C#'
ms.custom: seodec18
ms.date: 04/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.openlocfilehash: c72daa58d2fceb05d9cc9c388a9d2e5dbe062796
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422431"
---
# <a name="stackalloc-c-reference"></a>stackalloc (Referencia de C#)

La palabra clave `stackalloc` se usa para asignar un bloque de memoria en la pila.

```csharp
Span<int> block = stackalloc int[100];
```

La asignación del bloque asignado a un <xref:System.Span%601?displayName=nameWithType> en lugar de un `int*` permite las asignaciones de pila en un bloque seguro. No es necesario el contexto `unsafe`.

## <a name="remarks"></a>Comentarios

La palabra clave solo es válida en inicializadores de variables locales. El código siguiente genera errores del compilador.

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
Span<int> span;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
span = stackalloc int[100];
```

A partir de C# 7.3, puede usar la sintaxis de inicializador de matriz para matrices `stackalloc`. Todas las declaraciones siguientes declaran una matriz con tres elementos cuyos valores son los enteros `1`, `2` y `3`. La segunda inicialización asigna la memoria a un <xref:System.ReadOnlySpan%601>, lo que indica que no se puede modificar la memoria.

```csharp
// Valid starting with C# 7.3
Span<int> first = stackalloc int[3] { 1, 2, 3 };
ReadOnlySpan<int> second = stackalloc int[] { 1, 2, 3 };
Span<int> third = stackalloc[] { 1, 2, 3 };
```

Cuando se implican tipos de puntero, `stackalloc` requiere un contexto [unsafe](unsafe.md). Para obtener más información, vea [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md) (Código no seguro y punteros [Guía de programación de C#]).

`stackalloc` es como [_alloca](/cpp/c-runtime-library/reference/alloca) en la biblioteca en tiempo de ejecución de C.

## <a name="examples"></a>Ejemplos

En el ejemplo siguiente se calculan y muestran los 20 primeros números de la secuencia de Fibonacci. Cada número es la suma de los dos números anteriores. En el código, se asigna a la pila, no al montón, un bloque de memoria de tamaño suficiente para contener 20 elementos del tipo `int`. La dirección del bloque se almacena en el `Span` `fib`. Esta memoria no está sujeta a la recolección de elementos no utilizados y, por tanto, no necesita fijarse (mediante [fixed](fixed-statement.md)). La duración del bloque de memoria se limita a la duración del método que lo define. No se puede liberar la memoria antes de que el método vuelva.

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

En el ejemplo siguiente, se inicializa una matriz `stackalloc` de enteros en una máscara de bits con un bit establecido en cada elemento. Esto demuestra la nueva sintaxis de inicializador disponible a partir de C# 7.3:

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a>Seguridad

Debe usar <xref:System.Span%601> o <xref:System.ReadOnlySpan%601> cuando sea posible porque el código no administrado es menos seguro que las alternativas seguras. Incluso cuando se usa con punteros, el uso de `stackalloc` habilita automática las características de detección del búfer en el entorno Common Language Runtime (CLR). Si se detecta saturación del búfer, se finaliza el proceso lo antes posible para minimizar el riesgo de que se ejecute código malintencionado.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Código no seguro y punteros](../../programming-guide/unsafe-code-pointers/index.md)
