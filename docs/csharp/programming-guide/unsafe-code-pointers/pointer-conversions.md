---
title: "Conversiones de puntero (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
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
ms.openlocfilehash: e415d892d979e2bdcd648256150e2a96b1772ce4
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="dee73-102">Conversiones de puntero (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="dee73-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="dee73-103">En la tabla siguiente se muestran las conversiones de puntero implícitas predefinidas.</span><span class="sxs-lookup"><span data-stu-id="dee73-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="dee73-104">Las conversiones implícitas pueden ocurrir en muchas situaciones, incluidas las instrucciones de asignación y de invocación de método.</span><span class="sxs-lookup"><span data-stu-id="dee73-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="dee73-105">Conversiones de puntero implícitas</span><span class="sxs-lookup"><span data-stu-id="dee73-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="dee73-106">De</span><span class="sxs-lookup"><span data-stu-id="dee73-106">From</span></span>|<span data-ttu-id="dee73-107">Para</span><span class="sxs-lookup"><span data-stu-id="dee73-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="dee73-108">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="dee73-108">Any pointer type</span></span>|<span data-ttu-id="dee73-109">void*</span><span class="sxs-lookup"><span data-stu-id="dee73-109">void*</span></span>|  
|<span data-ttu-id="dee73-110">nulo</span><span class="sxs-lookup"><span data-stu-id="dee73-110">null</span></span>|<span data-ttu-id="dee73-111">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="dee73-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="dee73-112">La conversión de puntero explícita se usa para realizar conversiones, donde no existe ninguna conversión implícita, mediante una expresión de conversión.</span><span class="sxs-lookup"><span data-stu-id="dee73-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="dee73-113">En la siguiente tabla se muestran estas conversiones.</span><span class="sxs-lookup"><span data-stu-id="dee73-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="dee73-114">Conversiones de puntero explícitas</span><span class="sxs-lookup"><span data-stu-id="dee73-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="dee73-115">De</span><span class="sxs-lookup"><span data-stu-id="dee73-115">From</span></span>|<span data-ttu-id="dee73-116">Para</span><span class="sxs-lookup"><span data-stu-id="dee73-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="dee73-117">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="dee73-117">Any pointer type</span></span>|<span data-ttu-id="dee73-118">Cualquier otro tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="dee73-118">Any other pointer type</span></span>|  
|<span data-ttu-id="dee73-119">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="dee73-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="dee73-120">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="dee73-120">Any pointer type</span></span>|  
|<span data-ttu-id="dee73-121">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="dee73-121">Any pointer type</span></span>|<span data-ttu-id="dee73-122">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="dee73-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dee73-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dee73-123">Example</span></span>  
 <span data-ttu-id="dee73-124">En el ejemplo siguiente, un puntero a `int` se convierte en un puntero a `byte`.</span><span class="sxs-lookup"><span data-stu-id="dee73-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="dee73-125">Tenga en cuenta que el puntero señala al byte dirigido más bajo de la variable.</span><span class="sxs-lookup"><span data-stu-id="dee73-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="dee73-126">Cuando incrementa el resultado sucesivamente, hasta el tamaño de `int` (4 bytes), puede mostrar los bytes restantes de la variable.</span><span class="sxs-lookup"><span data-stu-id="dee73-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 <span data-ttu-id="dee73-127">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="dee73-127">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]</span></span>  
  
 <span data-ttu-id="dee73-128">[!code-cs[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="dee73-128">[!code-cs[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dee73-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="dee73-129">See Also</span></span>  
 <span data-ttu-id="dee73-130">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="dee73-130">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="dee73-131">[Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="dee73-131">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="dee73-132">[Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="dee73-132">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="dee73-133">[Tipos](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="dee73-133">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="dee73-134">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="dee73-134">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="dee73-135">[fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="dee73-135">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="dee73-136">stackalloc</span><span class="sxs-lookup"><span data-stu-id="dee73-136">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

