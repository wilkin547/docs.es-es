---
title: 'Conversiones de puntero: Guía de programación de C#'
description: Aprenda sobre las conversiones del puntero. Vea tablas de conversiones de puntero implícitas y explícitas y ejemplos de código, y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: c39be5cb52964abbea5bc5636c6fa74d8411a331
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382092"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="c5275-104">Conversiones de puntero (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="c5275-104">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="c5275-105">En la tabla siguiente se muestran las conversiones de puntero implícitas predefinidas.</span><span class="sxs-lookup"><span data-stu-id="c5275-105">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="c5275-106">Las conversiones implícitas pueden ocurrir en muchas situaciones, incluidas las instrucciones de asignación y de invocación de método.</span><span class="sxs-lookup"><span data-stu-id="c5275-106">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="c5275-107">Conversiones de puntero implícitas</span><span class="sxs-lookup"><span data-stu-id="c5275-107">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="c5275-108">De</span><span class="sxs-lookup"><span data-stu-id="c5275-108">From</span></span>|<span data-ttu-id="c5275-109">En</span><span class="sxs-lookup"><span data-stu-id="c5275-109">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="c5275-110">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="c5275-110">Any pointer type</span></span>|<span data-ttu-id="c5275-111">void\*</span><span class="sxs-lookup"><span data-stu-id="c5275-111">void\*</span></span>|  
|<span data-ttu-id="c5275-112">null</span><span class="sxs-lookup"><span data-stu-id="c5275-112">null</span></span>|<span data-ttu-id="c5275-113">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="c5275-113">Any pointer type</span></span>|  
  
 <span data-ttu-id="c5275-114">La conversión de puntero explícita se usa para realizar conversiones, donde no existe ninguna conversión implícita, mediante una expresión de conversión.</span><span class="sxs-lookup"><span data-stu-id="c5275-114">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="c5275-115">En la siguiente tabla se muestran estas conversiones.</span><span class="sxs-lookup"><span data-stu-id="c5275-115">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="c5275-116">Conversiones de puntero explícitas</span><span class="sxs-lookup"><span data-stu-id="c5275-116">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="c5275-117">De</span><span class="sxs-lookup"><span data-stu-id="c5275-117">From</span></span>|<span data-ttu-id="c5275-118">En</span><span class="sxs-lookup"><span data-stu-id="c5275-118">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="c5275-119">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="c5275-119">Any pointer type</span></span>|<span data-ttu-id="c5275-120">Cualquier otro tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="c5275-120">Any other pointer type</span></span>|  
|<span data-ttu-id="c5275-121">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="c5275-121">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="c5275-122">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="c5275-122">Any pointer type</span></span>|  
|<span data-ttu-id="c5275-123">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="c5275-123">Any pointer type</span></span>|<span data-ttu-id="c5275-124">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="c5275-124">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c5275-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5275-125">Example</span></span>  
 <span data-ttu-id="c5275-126">En el ejemplo siguiente, un puntero a `int` se convierte en un puntero a `byte`.</span><span class="sxs-lookup"><span data-stu-id="c5275-126">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="c5275-127">Tenga en cuenta que el puntero señala al byte dirigido más bajo de la variable.</span><span class="sxs-lookup"><span data-stu-id="c5275-127">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="c5275-128">Cuando incrementa el resultado sucesivamente, hasta el tamaño de `int` (4 bytes), puede mostrar los bytes restantes de la variable.</span><span class="sxs-lookup"><span data-stu-id="c5275-128">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="c5275-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5275-129">See also</span></span>

- [<span data-ttu-id="c5275-130">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c5275-130">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c5275-131">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="c5275-131">Pointer types</span></span>](pointer-types.md)
- [<span data-ttu-id="c5275-132">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="c5275-132">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="c5275-133">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="c5275-133">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="c5275-134">unsafe</span><span class="sxs-lookup"><span data-stu-id="c5275-134">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="c5275-135">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c5275-135">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="c5275-136">stackalloc</span><span class="sxs-lookup"><span data-stu-id="c5275-136">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
