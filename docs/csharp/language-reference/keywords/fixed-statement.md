---
title: "fixed (Instrucción, Referencia de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- fixed_CSharpKeyword
- fixed
dev_langs:
- CSharp
helpviewer_keywords:
- fixed keyword [C#]
ms.assetid: 7ea6db08-ad49-4a7a-b934-d8c4acad1c3a
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4e1f810f6e6cfaef3a65c7391f074b414ef18b5a
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="fixed-statement-c-reference"></a>fixed (Instrucción, Referencia de C#)
La instrucción `fixed` evita que el recolector de elementos no utilizados reubique una variable móvil. La instrucción `fixed` solo se permite en un contexto de [unsafe](../../../csharp/language-reference/keywords/unsafe.md). `Fixed` también puede usarse para crear [búferes de tamaño fijo](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).  
  
 La instrucción `fixed` establece un puntero a una variable administrada y "ancla" esa variable durante su ejecución. Sin `fixed`, los punteros a variables administradas móviles serían de poca utilidad, puesto que la recolección de elementos no utilizados podría reubicar las variables de forma impredecible. El compilador de C# solo permite asignar un puntero a una variable administrada en una instrucción `fixed`.  
  
 [!code-cs[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_1.cs)]  
  
 Puede inicializar un puntero mediante una matriz, una cadena, un búfer de tamaño fijo o la dirección de una variable. En el ejemplo siguiente se muestra el uso de direcciones, matrices y cadenas de variables. Para obtener más información sobre los búferes de tamaño fijo, consulte [Fixed Size Buffers](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md) (Búferes de tamaño fijo).  
  
 [!code-cs[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_2.cs)]  
  
 Puede inicializar varios punteros, siempre que sean del mismo tipo.  
  
```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}  
```
  
 Para inicializar punteros de tipos diferentes, simplemente anide instrucciones `fixed`, como se muestra en el ejemplo siguiente.  
  
 [!code-cs[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_3.cs)]  
  
 Después de ejecutar el código de la instrucción, las variables ancladas se desanclan y quedan sujetas a la recolección de elementos no utilizados. Por lo tanto, no debe apuntar a esas variables fuera de la instrucción `fixed`.  
  
> [!NOTE]
>  Los punteros inicializados en instrucciones fijas no pueden modificarse.  
  
 En el modo no seguro, puede asignar memoria en la pila, en la que no está sujeta a la recolección de elementos no utilizados y, por tanto, no necesita anclarse. Para obtener más información, consulte [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csrefKeywordsFixedLock#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_4.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [Búferes de tamaño fijo](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)

