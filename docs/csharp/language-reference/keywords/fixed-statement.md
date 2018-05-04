---
title: fixed (Instrucción, Referencia de C#)
ms.date: 04/20/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5dd117461f792ec7a10b740fbad277de52d05623
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="fixed-statement-c-reference"></a>fixed (Instrucción, Referencia de C#)

La instrucción `fixed` evita que el recolector de elementos no utilizados reubique una variable móvil. La instrucción `fixed` solo se permite en un contexto de [unsafe](unsafe.md). `Fixed` también puede usarse para crear [búferes de tamaño fijo](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).

La instrucción `fixed` establece un puntero a una variable administrada y "ancla" esa variable durante su ejecución. Los punteros a variables administradas móviles solo son útiles en un contexto `fixed`. Sin un contexto `fixed`, la recolección de elementos no utilizados podría reubicar las variables de forma impredecible. El compilador de C# solo permite asignar un puntero a una variable administrada en una instrucción `fixed`.

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

Puede inicializar un puntero mediante una matriz, una cadena, un búfer de tamaño fijo o la dirección de una variable. En el ejemplo siguiente se muestra el uso de direcciones, matrices y cadenas de variables. Para obtener más información sobre los búferes de tamaño fijo, consulte [Fixed Size Buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md) (Búferes de tamaño fijo).

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

Es posible inicializar varios punteros en una sola instrucción si todos son del mismo tipo:

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

Para inicializar punteros de tipos diferentes, simplemente anide instrucciones `fixed`, como se muestra en el ejemplo siguiente.

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

Después de ejecutar el código de la instrucción, las variables ancladas se desanclan y quedan sujetas a la recolección de elementos no utilizados. Por lo tanto, no debe apuntar a esas variables fuera de la instrucción `fixed`. Las variables declaradas en la instrucción `fixed` se limitan a dicha instrucción, lo que simplifica esta tarea:

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

Los punteros inicializados en instrucciones `fixed` son variables de solo lectura. Si quiere modificar el valor del puntero, debe declarar una segunda variable de puntero y modificarla. La variable declarada en la instrucción `fixed` no se puede modificar:

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```


En el modo no seguro, puede asignar memoria en la pila, en la que no está sujeta a la recolección de elementos no utilizados y, por tanto, no necesita anclarse. Para obtener más información, consulte [stackalloc](stackalloc.md).

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#4)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

 [Referencia de C#](../index.md)  
 [Guía de programación de C#](../../programming-guide/index.md)  
 [Palabras clave de C#](index.md)  
 [unsafe](unsafe.md)  
 [Búferes de tamaño fijo](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
