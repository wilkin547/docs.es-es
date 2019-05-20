---
title: 'Cómo: Obtener el valor de una variable de puntero (Guía de programación de C#)'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: 9a10bcc809f3ecbc9a0fa9b917940b8e030fab8f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635096"
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="d5c8d-102">Cómo: Obtener el valor de una variable de puntero (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d5c8d-102">How to: obtain the value of a pointer variable (C# Programming Guide)</span></span>

<span data-ttu-id="d5c8d-103">Use el operador de direccionamiento indirecto del puntero para obtener la variable en la ubicación indicada por un puntero.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="d5c8d-104">La expresión tiene el formato siguiente, donde `p` es un tipo de puntero:</span><span class="sxs-lookup"><span data-stu-id="d5c8d-104">The expression takes the following form, where `p` is a pointer type:</span></span>  

```csharp
*p;  
```

<span data-ttu-id="d5c8d-105">No se puede usar el operador de direccionamiento indirecto unario en una expresión de cualquier tipo distinta de la del tipo de puntero.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="d5c8d-106">Tampoco se puede aplicar a un puntero [void](../../../csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="d5c8d-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  

<span data-ttu-id="d5c8d-107">Cuando se aplica el operador de direccionamiento indirecto a un puntero [null](../../../csharp/language-reference/keywords/null.md), el resultado depende de la implementación.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  

## <a name="example"></a><span data-ttu-id="d5c8d-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5c8d-108">Example</span></span>

<span data-ttu-id="d5c8d-109">En el ejemplo siguiente, se tiene acceso a una variable del tipo `char` mediante punteros de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="d5c8d-110">Hay que tener en cuenta que la dirección de `theChar` variará de una ejecución a otra porque la dirección física asignada a una variable puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  

 [!code-csharp[csProgGuidePointers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#5)]  

 [!code-csharp[csProgGuidePointers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#6)]  
  
<span data-ttu-id="d5c8d-111">**Valor de theChar = Z**</span><span class="sxs-lookup"><span data-stu-id="d5c8d-111">**Value of theChar = Z**</span></span>  
<span data-ttu-id="d5c8d-112">**Dirección de theChar = 12F718**</span><span class="sxs-lookup"><span data-stu-id="d5c8d-112">**Address of theChar = 12F718**</span></span>  
<span data-ttu-id="d5c8d-113">**Valor de pChar = Z**</span><span class="sxs-lookup"><span data-stu-id="d5c8d-113">**Value of pChar = Z**</span></span>  
<span data-ttu-id="d5c8d-114">**Valor de pInt = 90**</span><span class="sxs-lookup"><span data-stu-id="d5c8d-114">**Value of pInt = 90**</span></span>  

## <a name="see-also"></a><span data-ttu-id="d5c8d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5c8d-115">See also</span></span>

- [<span data-ttu-id="d5c8d-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d5c8d-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d5c8d-117">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="d5c8d-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="d5c8d-118">Tipos</span><span class="sxs-lookup"><span data-stu-id="d5c8d-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="d5c8d-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="d5c8d-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="d5c8d-120">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d5c8d-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="d5c8d-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="d5c8d-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
