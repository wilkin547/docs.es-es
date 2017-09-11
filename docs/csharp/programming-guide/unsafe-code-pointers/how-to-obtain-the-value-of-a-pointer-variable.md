---
title: "Cómo: Obtener el valor de una variable de puntero (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
caps.latest.revision: 17
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
ms.openlocfilehash: 4cff42de07f2edb279ddd1cafefe9f4b67a38ce1
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="57518-102">Cómo: Obtener el valor de una variable de puntero (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="57518-102">How to: Obtain the Value of a Pointer Variable (C# Programming Guide)</span></span>
<span data-ttu-id="57518-103">Use el operador de direccionamiento indirecto del puntero para obtener la variable en la ubicación indicada por un puntero.</span><span class="sxs-lookup"><span data-stu-id="57518-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="57518-104">La expresión tiene el formato siguiente, donde `p` es un tipo de puntero:</span><span class="sxs-lookup"><span data-stu-id="57518-104">The expression takes the following form, where `p` is a pointer type:</span></span>  
  
```  
*p;  
```  
  
 <span data-ttu-id="57518-105">No se puede usar el operador de direccionamiento indirecto unario en una expresión de cualquier tipo distinta de la del tipo de puntero.</span><span class="sxs-lookup"><span data-stu-id="57518-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="57518-106">Tampoco se puede aplicar a un puntero [void](../../../csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="57518-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  
  
 <span data-ttu-id="57518-107">Cuando se aplica el operador de direccionamiento indirecto a un puntero [null](../../../csharp/language-reference/keywords/null.md), el resultado depende de la implementación.</span><span class="sxs-lookup"><span data-stu-id="57518-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57518-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57518-108">Example</span></span>  
 <span data-ttu-id="57518-109">En el ejemplo siguiente, se tiene acceso a una variable del tipo `char` mediante punteros de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="57518-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="57518-110">Hay que tener en cuenta que la dirección de `theChar` variará de una ejecución a otra porque la dirección física asignada a una variable puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="57518-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  
  
 <span data-ttu-id="57518-111">[!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="57518-111">[!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]</span></span>  
  
 <span data-ttu-id="57518-112">[!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="57518-112">[!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]</span></span>  
  
 <span data-ttu-id="57518-113">**Valor de theChar = Z** </span><span class="sxs-lookup"><span data-stu-id="57518-113">**Value of theChar = Z** </span></span>  
<span data-ttu-id="57518-114">**Dirección de theChar = 12F718**</span><span class="sxs-lookup"><span data-stu-id="57518-114">**Address of theChar = 12F718**</span></span>  
<span data-ttu-id="57518-115">**Valor de pChar = Z** </span><span class="sxs-lookup"><span data-stu-id="57518-115">**Value of pChar = Z** </span></span>  
<span data-ttu-id="57518-116">**Valor de pInt = 90**</span><span class="sxs-lookup"><span data-stu-id="57518-116">**Value of pInt = 90**</span></span>    
## <a name="see-also"></a><span data-ttu-id="57518-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="57518-117">See Also</span></span>  
 <span data-ttu-id="57518-118">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="57518-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="57518-119">[Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="57518-119">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="57518-120">[Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="57518-120">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="57518-121">[Tipos](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="57518-121">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="57518-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="57518-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="57518-123">[fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="57518-123">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="57518-124">stackalloc</span><span class="sxs-lookup"><span data-stu-id="57518-124">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

