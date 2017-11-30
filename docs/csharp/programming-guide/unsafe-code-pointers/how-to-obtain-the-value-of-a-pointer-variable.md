---
title: "Cómo: Obtener el valor de una variable de puntero (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8065c10bec737789f13dcbafe147b50eedb9da36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="98798-102">Cómo: Obtener el valor de una variable de puntero (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="98798-102">How to: Obtain the Value of a Pointer Variable (C# Programming Guide)</span></span>
<span data-ttu-id="98798-103">Use el operador de direccionamiento indirecto del puntero para obtener la variable en la ubicación indicada por un puntero.</span><span class="sxs-lookup"><span data-stu-id="98798-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="98798-104">La expresión tiene el formato siguiente, donde `p` es un tipo de puntero:</span><span class="sxs-lookup"><span data-stu-id="98798-104">The expression takes the following form, where `p` is a pointer type:</span></span>  
  
```  
*p;  
```  
  
 <span data-ttu-id="98798-105">No se puede usar el operador de direccionamiento indirecto unario en una expresión de cualquier tipo distinta de la del tipo de puntero.</span><span class="sxs-lookup"><span data-stu-id="98798-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="98798-106">Tampoco se puede aplicar a un puntero [void](../../../csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="98798-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  
  
 <span data-ttu-id="98798-107">Cuando se aplica el operador de direccionamiento indirecto a un puntero [null](../../../csharp/language-reference/keywords/null.md), el resultado depende de la implementación.</span><span class="sxs-lookup"><span data-stu-id="98798-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98798-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98798-108">Example</span></span>  
 <span data-ttu-id="98798-109">En el ejemplo siguiente, se tiene acceso a una variable del tipo `char` mediante punteros de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="98798-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="98798-110">Hay que tener en cuenta que la dirección de `theChar` variará de una ejecución a otra porque la dirección física asignada a una variable puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="98798-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  
  
 [!code-csharp[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]  
  
 <span data-ttu-id="98798-111">**Valor de theChar = Z**</span><span class="sxs-lookup"><span data-stu-id="98798-111">**Value of theChar = Z**</span></span>  
<span data-ttu-id="98798-112">**Dirección de theChar = 12F718**</span><span class="sxs-lookup"><span data-stu-id="98798-112">**Address of theChar = 12F718**</span></span>  
<span data-ttu-id="98798-113">**Valor de pChar = Z** </span><span class="sxs-lookup"><span data-stu-id="98798-113">**Value of pChar = Z** </span></span>  
<span data-ttu-id="98798-114">**Valor de pInt = 90**</span><span class="sxs-lookup"><span data-stu-id="98798-114">**Value of pInt = 90**</span></span>    
## <a name="see-also"></a><span data-ttu-id="98798-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="98798-115">See Also</span></span>  
 [<span data-ttu-id="98798-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="98798-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="98798-117">Expresiones de puntero</span><span class="sxs-lookup"><span data-stu-id="98798-117">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="98798-118">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="98798-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="98798-119">Tipos</span><span class="sxs-lookup"><span data-stu-id="98798-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="98798-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="98798-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="98798-121">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="98798-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="98798-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="98798-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
