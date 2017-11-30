---
title: unsafe (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords: unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1fffbe36e39d279b2364b178188381a403c8ff86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="86853-102">unsafe (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="86853-102">unsafe (C# Reference)</span></span>
<span data-ttu-id="86853-103">La palabra clave `unsafe` denota un contexto no seguro, que es necesario para realizar cualquier operación que implique punteros.</span><span class="sxs-lookup"><span data-stu-id="86853-103">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="86853-104">Para obtener más información, vea [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) (Código no seguro y punteros [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="86853-104">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="86853-105">Puede usar el codificador `unsafe` en la declaración de un tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="86853-105">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="86853-106">Por consiguiente, toda la extensión textual del tipo o miembro se considera un contexto no seguro.</span><span class="sxs-lookup"><span data-stu-id="86853-106">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="86853-107">Por ejemplo, el siguiente método se declara con el modificador `unsafe`:</span><span class="sxs-lookup"><span data-stu-id="86853-107">For example, the following is a method declared with the `unsafe` modifier:</span></span>  
  
```  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="86853-108">El ámbito del contexto no seguro se extiende desde la lista de parámetros hasta el final del método, por lo que también pueden usarse punteros en la lista de parámetros:</span><span class="sxs-lookup"><span data-stu-id="86853-108">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>  
  
```  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 <span data-ttu-id="86853-109">También puede usarse un bloque no seguro para habilitar el uso de código no seguro en el bloque.</span><span class="sxs-lookup"><span data-stu-id="86853-109">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="86853-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="86853-110">For example:</span></span>  
  
```  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="86853-111">Para compilar código no seguro, debe especificar la opción [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) del compilador.</span><span class="sxs-lookup"><span data-stu-id="86853-111">To compile unsafe code, you must specify the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="86853-112">Common Language Runtime no puede comprobar el código no seguro.</span><span class="sxs-lookup"><span data-stu-id="86853-112">Unsafe code is not verifiable by the common language runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86853-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="86853-113">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="86853-114">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="86853-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="86853-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="86853-115">See Also</span></span>  
 [<span data-ttu-id="86853-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="86853-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="86853-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="86853-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="86853-118">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="86853-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="86853-119">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="86853-119">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="86853-120">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="86853-120">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="86853-121">Búferes de tamaño fijo</span><span class="sxs-lookup"><span data-stu-id="86853-121">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
