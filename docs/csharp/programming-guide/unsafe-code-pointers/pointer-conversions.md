---
title: 'Conversiones de puntero: Guía de programación de C#'
description: Aprenda sobre las conversiones del puntero. Vea tablas de conversiones de puntero implícitas y explícitas y ejemplos de código, y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 7a37c4e9f6333c00c7842df0fdaf353df516974d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205079"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="860c5-104">Conversiones de puntero (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="860c5-104">Pointer Conversions (C# Programming Guide)</span></span>

<span data-ttu-id="860c5-105">En la tabla siguiente se muestran las conversiones de puntero implícitas predefinidas.</span><span class="sxs-lookup"><span data-stu-id="860c5-105">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="860c5-106">Las conversiones implícitas pueden ocurrir en muchas situaciones, incluidas las instrucciones de asignación y de invocación de método.</span><span class="sxs-lookup"><span data-stu-id="860c5-106">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="860c5-107">Conversiones de puntero implícitas</span><span class="sxs-lookup"><span data-stu-id="860c5-107">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="860c5-108">De</span><span class="sxs-lookup"><span data-stu-id="860c5-108">From</span></span>|<span data-ttu-id="860c5-109">En</span><span class="sxs-lookup"><span data-stu-id="860c5-109">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="860c5-110">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="860c5-110">Any pointer type</span></span>|<span data-ttu-id="860c5-111">void\*</span><span class="sxs-lookup"><span data-stu-id="860c5-111">void\*</span></span>|  
|<span data-ttu-id="860c5-112">null</span><span class="sxs-lookup"><span data-stu-id="860c5-112">null</span></span>|<span data-ttu-id="860c5-113">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="860c5-113">Any pointer type</span></span>|  
  
 <span data-ttu-id="860c5-114">La conversión de puntero explícita se usa para realizar conversiones, donde no existe ninguna conversión implícita, mediante una expresión de conversión.</span><span class="sxs-lookup"><span data-stu-id="860c5-114">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="860c5-115">En la siguiente tabla se muestran estas conversiones.</span><span class="sxs-lookup"><span data-stu-id="860c5-115">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="860c5-116">Conversiones de puntero explícitas</span><span class="sxs-lookup"><span data-stu-id="860c5-116">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="860c5-117">De</span><span class="sxs-lookup"><span data-stu-id="860c5-117">From</span></span>|<span data-ttu-id="860c5-118">En</span><span class="sxs-lookup"><span data-stu-id="860c5-118">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="860c5-119">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="860c5-119">Any pointer type</span></span>|<span data-ttu-id="860c5-120">Cualquier otro tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="860c5-120">Any other pointer type</span></span>|  
|<span data-ttu-id="860c5-121">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="860c5-121">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="860c5-122">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="860c5-122">Any pointer type</span></span>|  
|<span data-ttu-id="860c5-123">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="860c5-123">Any pointer type</span></span>|<span data-ttu-id="860c5-124">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="860c5-124">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="860c5-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="860c5-125">Example</span></span>  

 <span data-ttu-id="860c5-126">En el ejemplo siguiente, un puntero a `int` se convierte en un puntero a `byte`.</span><span class="sxs-lookup"><span data-stu-id="860c5-126">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="860c5-127">Tenga en cuenta que el puntero señala al byte dirigido más bajo de la variable.</span><span class="sxs-lookup"><span data-stu-id="860c5-127">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="860c5-128">Cuando incrementa el resultado sucesivamente, hasta el tamaño de `int` (4 bytes), puede mostrar los bytes restantes de la variable.</span><span class="sxs-lookup"><span data-stu-id="860c5-128">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="860c5-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="860c5-129">See also</span></span>

- [<span data-ttu-id="860c5-130">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="860c5-130">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="860c5-131">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="860c5-131">Pointer types</span></span>](pointer-types.md)
- [<span data-ttu-id="860c5-132">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="860c5-132">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="860c5-133">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="860c5-133">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="860c5-134">unsafe</span><span class="sxs-lookup"><span data-stu-id="860c5-134">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="860c5-135">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="860c5-135">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="860c5-136">stackalloc</span><span class="sxs-lookup"><span data-stu-id="860c5-136">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
