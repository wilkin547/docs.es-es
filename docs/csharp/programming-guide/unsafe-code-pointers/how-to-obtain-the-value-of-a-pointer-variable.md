---
title: 'Procedimiento Obtener el valor de una variable de puntero: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: b20642344b34b5426512ef64bde2ab33d55136b9
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236640"
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="5827a-102">Procedimiento Obtener el valor de una variable de puntero (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="5827a-102">How to: Obtain the Value of a Pointer Variable (C# Programming Guide)</span></span>
<span data-ttu-id="5827a-103">Use el operador de direccionamiento indirecto del puntero para obtener la variable en la ubicación indicada por un puntero.</span><span class="sxs-lookup"><span data-stu-id="5827a-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="5827a-104">La expresión tiene el formato siguiente, donde `p` es un tipo de puntero:</span><span class="sxs-lookup"><span data-stu-id="5827a-104">The expression takes the following form, where `p` is a pointer type:</span></span>  
  
```  
*p;  
```  
  
 <span data-ttu-id="5827a-105">No se puede usar el operador de direccionamiento indirecto unario en una expresión de cualquier tipo distinta de la del tipo de puntero.</span><span class="sxs-lookup"><span data-stu-id="5827a-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="5827a-106">Tampoco se puede aplicar a un puntero [void](../../../csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="5827a-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  
  
 <span data-ttu-id="5827a-107">Cuando se aplica el operador de direccionamiento indirecto a un puntero [null](../../../csharp/language-reference/keywords/null.md), el resultado depende de la implementación.</span><span class="sxs-lookup"><span data-stu-id="5827a-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5827a-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5827a-108">Example</span></span>  
 <span data-ttu-id="5827a-109">En el ejemplo siguiente, se tiene acceso a una variable del tipo `char` mediante punteros de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="5827a-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="5827a-110">Hay que tener en cuenta que la dirección de `theChar` variará de una ejecución a otra porque la dirección física asignada a una variable puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="5827a-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  
  
 [!code-csharp[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]  
  
<span data-ttu-id="5827a-111">**Valor de theChar = Z**
**Dirección de theChar = 12F718**
**Valor de pChar = Z**
**Valor de pInt = 90**</span><span class="sxs-lookup"><span data-stu-id="5827a-111">**Value of theChar = Z**
**Address of theChar = 12F718**
**Value of pChar = Z**
**Value of pInt = 90**</span></span>

## <a name="see-also"></a><span data-ttu-id="5827a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="5827a-112">See Also</span></span>

- [<span data-ttu-id="5827a-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5827a-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="5827a-114">Expresiones de puntero</span><span class="sxs-lookup"><span data-stu-id="5827a-114">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="5827a-115">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="5827a-115">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="5827a-116">Tipos</span><span class="sxs-lookup"><span data-stu-id="5827a-116">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="5827a-117">unsafe</span><span class="sxs-lookup"><span data-stu-id="5827a-117">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="5827a-118">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5827a-118">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="5827a-119">stackalloc</span><span class="sxs-lookup"><span data-stu-id="5827a-119">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
