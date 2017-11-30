---
title: "Conversiones de puntero (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 36589d139c91e04d9e3d8b31281a91c26b85a5d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="7dd6e-102">Conversiones de puntero (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7dd6e-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="7dd6e-103">En la tabla siguiente se muestran las conversiones de puntero implícitas predefinidas.</span><span class="sxs-lookup"><span data-stu-id="7dd6e-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="7dd6e-104">Las conversiones implícitas pueden ocurrir en muchas situaciones, incluidas las instrucciones de asignación y de invocación de método.</span><span class="sxs-lookup"><span data-stu-id="7dd6e-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="7dd6e-105">Conversiones de puntero implícitas</span><span class="sxs-lookup"><span data-stu-id="7dd6e-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="7dd6e-106">De</span><span class="sxs-lookup"><span data-stu-id="7dd6e-106">From</span></span>|<span data-ttu-id="7dd6e-107">Para</span><span class="sxs-lookup"><span data-stu-id="7dd6e-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="7dd6e-108">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="7dd6e-108">Any pointer type</span></span>|<span data-ttu-id="7dd6e-109">void*</span><span class="sxs-lookup"><span data-stu-id="7dd6e-109">void*</span></span>|  
|<span data-ttu-id="7dd6e-110">nulo</span><span class="sxs-lookup"><span data-stu-id="7dd6e-110">null</span></span>|<span data-ttu-id="7dd6e-111">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="7dd6e-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="7dd6e-112">La conversión de puntero explícita se usa para realizar conversiones, donde no existe ninguna conversión implícita, mediante una expresión de conversión.</span><span class="sxs-lookup"><span data-stu-id="7dd6e-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="7dd6e-113">En la siguiente tabla se muestran estas conversiones.</span><span class="sxs-lookup"><span data-stu-id="7dd6e-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="7dd6e-114">Conversiones de puntero explícitas</span><span class="sxs-lookup"><span data-stu-id="7dd6e-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="7dd6e-115">De</span><span class="sxs-lookup"><span data-stu-id="7dd6e-115">From</span></span>|<span data-ttu-id="7dd6e-116">Para</span><span class="sxs-lookup"><span data-stu-id="7dd6e-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="7dd6e-117">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="7dd6e-117">Any pointer type</span></span>|<span data-ttu-id="7dd6e-118">Cualquier otro tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="7dd6e-118">Any other pointer type</span></span>|  
|<span data-ttu-id="7dd6e-119">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="7dd6e-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="7dd6e-120">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="7dd6e-120">Any pointer type</span></span>|  
|<span data-ttu-id="7dd6e-121">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="7dd6e-121">Any pointer type</span></span>|<span data-ttu-id="7dd6e-122">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="7dd6e-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7dd6e-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7dd6e-123">Example</span></span>  
 <span data-ttu-id="7dd6e-124">En el ejemplo siguiente, un puntero a `int` se convierte en un puntero a `byte`.</span><span class="sxs-lookup"><span data-stu-id="7dd6e-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="7dd6e-125">Tenga en cuenta que el puntero señala al byte dirigido más bajo de la variable.</span><span class="sxs-lookup"><span data-stu-id="7dd6e-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="7dd6e-126">Cuando incrementa el resultado sucesivamente, hasta el tamaño de `int` (4 bytes), puede mostrar los bytes restantes de la variable.</span><span class="sxs-lookup"><span data-stu-id="7dd6e-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7dd6e-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="7dd6e-127">See Also</span></span>  
 [<span data-ttu-id="7dd6e-128">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7dd6e-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7dd6e-129">Expresiones de puntero</span><span class="sxs-lookup"><span data-stu-id="7dd6e-129">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="7dd6e-130">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="7dd6e-130">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="7dd6e-131">Tipos</span><span class="sxs-lookup"><span data-stu-id="7dd6e-131">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="7dd6e-132">unsafe</span><span class="sxs-lookup"><span data-stu-id="7dd6e-132">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="7dd6e-133">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7dd6e-133">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="7dd6e-134">stackalloc</span><span class="sxs-lookup"><span data-stu-id="7dd6e-134">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
