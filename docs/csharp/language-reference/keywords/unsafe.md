---
title: unsafe (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
dev_langs:
- CSharp
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
caps.latest.revision: 19
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
ms.openlocfilehash: ceba9e518caf6618cf2f457b930ce08f18273d8c
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="unsafe-c-reference"></a><span data-ttu-id="d94b4-102">unsafe (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d94b4-102">unsafe (C# Reference)</span></span>
<span data-ttu-id="d94b4-103">La palabra clave `unsafe` denota un contexto no seguro, que es necesario para realizar cualquier operación que implique punteros.</span><span class="sxs-lookup"><span data-stu-id="d94b4-103">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="d94b4-104">Para obtener más información, vea [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) (Código no seguro y punteros [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="d94b4-104">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="d94b4-105">Puede usar el codificador `unsafe` en la declaración de un tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="d94b4-105">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="d94b4-106">Por consiguiente, toda la extensión textual del tipo o miembro se considera un contexto no seguro.</span><span class="sxs-lookup"><span data-stu-id="d94b4-106">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="d94b4-107">Por ejemplo, el siguiente método se declara con el modificador `unsafe`:</span><span class="sxs-lookup"><span data-stu-id="d94b4-107">For example, the following is a method declared with the `unsafe` modifier:</span></span>  
  
```  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="d94b4-108">El ámbito del contexto no seguro se extiende desde la lista de parámetros hasta el final del método, por lo que también pueden usarse punteros en la lista de parámetros:</span><span class="sxs-lookup"><span data-stu-id="d94b4-108">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>  
  
```  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 <span data-ttu-id="d94b4-109">También puede usarse un bloque no seguro para habilitar el uso de código no seguro en el bloque.</span><span class="sxs-lookup"><span data-stu-id="d94b4-109">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="d94b4-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d94b4-110">For example:</span></span>  
  
```  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="d94b4-111">Para compilar código no seguro, debe especificar la opción [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) del compilador.</span><span class="sxs-lookup"><span data-stu-id="d94b4-111">To compile unsafe code, you must specify the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="d94b4-112">Common Language Runtime no puede comprobar el código no seguro.</span><span class="sxs-lookup"><span data-stu-id="d94b4-112">Unsafe code is not verifiable by the common language runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d94b4-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d94b4-113">Example</span></span>  
 <span data-ttu-id="d94b4-114">[!code-cs[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d94b4-114">[!code-cs[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d94b4-115">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="d94b4-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d94b4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d94b4-116">See Also</span></span>  
 <span data-ttu-id="d94b4-117">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d94b4-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d94b4-118">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d94b4-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d94b4-119">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d94b4-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="d94b4-120">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md)  (fixed [Instrucción, Referencia de C#])</span><span class="sxs-lookup"><span data-stu-id="d94b4-120">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 <span data-ttu-id="d94b4-121">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  (Código no seguro y punteros [Guía de programación de C#])</span><span class="sxs-lookup"><span data-stu-id="d94b4-121">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 [<span data-ttu-id="d94b4-122">Búferes de tamaño fijo</span><span class="sxs-lookup"><span data-stu-id="d94b4-122">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)

