---
title: stackalloc (Referencia de C#)
ms.date: 04/12/2018
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.openlocfilehash: 5926550eea1f5a2f8fb74645f22ca54c2bed3136
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43508585"
---
# <a name="stackalloc-c-reference"></a>stackalloc (Referencia de C#)
La palabra clave `stackalloc` se usa en un contexto de código no seguro para asignar un bloque de memoria a la pila.

```csharp
int* block = stackalloc int[100];
```

## <a name="remarks"></a>Comentarios

La palabra clave solo es válida en inicializadores de variables locales. El código siguiente genera errores del compilador.

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
```

A partir de C# 7.3, puede usar la sintaxis de inicializador de matriz para matrices `stackalloc`. Todas las declaraciones siguientes declaran una matriz con tres elementos cuyos valores son los enteros `1`, `2` y `3`:

```csharp
// Valid starting with C# 7.3
int* first = stackalloc int[3] { 1, 2, 3 };
int* second = stackalloc int[] { 1, 2, 3 };
int* third = stackalloc[] { 1, 2, 3 };
```

Como implica tipos de puntero, `stackalloc` requiere un contexto [unsafe](unsafe.md). Para obtener más información, vea [Código no seguro y punteros](../../programming-guide/unsafe-code-pointers/index.md). 

`stackalloc` es como [_alloca](/cpp/c-runtime-library/reference/alloca) en la biblioteca en tiempo de ejecución de C.

## <a name="examples"></a>Ejemplos

En el ejemplo siguiente se calculan y muestran los 20 primeros números de la secuencia de Fibonacci. Cada número es la suma de los dos números anteriores. En el código, se asigna a la pila, no al montón, un bloque de memoria de tamaño suficiente para contener 20 elementos del tipo `int`. La dirección del bloque se almacena en el puntero `fib`. Esta memoria no está sujeta a la recolección de elementos no utilizados y, por tanto, no necesita fijarse (mediante [fixed](fixed-statement.md)). La duración del bloque de memoria se limita a la duración del método que lo define. No se puede liberar la memoria antes de que el método vuelva.

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

En el ejemplo siguiente, se inicializa una matriz `stackalloc` de enteros en una máscara de bits con un bit establecido en cada elemento. Esto demuestra la nueva sintaxis de inicializador disponible a partir de C# 7.3:

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a>Seguridad

El código no seguro es menos seguro que las alternativas seguras. Pero el uso de `stackalloc` habilita automáticamente las características de detección de saturación del búfer en el entorno Common Language Runtime (CLR). Si se detecta saturación del búfer, se finaliza el proceso lo antes posible para minimizar el riesgo de que se ejecute código malintencionado.

## <a name="c-language-specification"></a>Especificación del lenguaje C#
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
- [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)  
- [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
