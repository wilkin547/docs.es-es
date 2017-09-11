---
title: void (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- void_CSharpKeyword
- void
dev_langs:
- CSharp
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
caps.latest.revision: 15
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
ms.openlocfilehash: d1bd7ece5ce3b558c616a4eb3a4668c3c13eb1cb
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="void-c-reference"></a><span data-ttu-id="636ea-102">void (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="636ea-102">void (C# Reference)</span></span>
<span data-ttu-id="636ea-103">Cuando se usa como tipo de valor devuelto para un método, `void` especifica que el método no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="636ea-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="636ea-104">`void` no se permite en la lista de parámetros de un método.</span><span class="sxs-lookup"><span data-stu-id="636ea-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="636ea-105">Un método que no usa parámetros y que no devuelve ningún valor se declara del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="636ea-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="636ea-106">`void` también se usa en un contexto no seguro para declarar un puntero a un tipo desconocido.</span><span class="sxs-lookup"><span data-stu-id="636ea-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="636ea-107">Para obtener más información, vea [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="636ea-107">For more information, see [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="636ea-108">`void` es un alias del tipo <xref:System.Void?displayProperty=fullName> de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="636ea-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=fullName> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="636ea-109">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="636ea-109">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="636ea-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="636ea-110">See also</span></span>
 <span data-ttu-id="636ea-111">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="636ea-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="636ea-112">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="636ea-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="636ea-113">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="636ea-113">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="636ea-114">[Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="636ea-114">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 <span data-ttu-id="636ea-115">[Tipos de valor](../../../csharp/language-reference/keywords/value-types.md) </span><span class="sxs-lookup"><span data-stu-id="636ea-115">[Value Types](../../../csharp/language-reference/keywords/value-types.md) </span></span>  
 <span data-ttu-id="636ea-116">[Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md) </span><span class="sxs-lookup"><span data-stu-id="636ea-116">[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md) </span></span>  
 [<span data-ttu-id="636ea-117">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="636ea-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)

