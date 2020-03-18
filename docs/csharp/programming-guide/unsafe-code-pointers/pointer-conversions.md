---
title: 'Conversiones de puntero: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 517166331d2bcf73132269ce2adcf68d5f60b4fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76745366"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="945ff-102">Conversiones de puntero (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="945ff-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="945ff-103">En la tabla siguiente se muestran las conversiones de puntero implícitas predefinidas.</span><span class="sxs-lookup"><span data-stu-id="945ff-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="945ff-104">Las conversiones implícitas pueden ocurrir en muchas situaciones, incluidas las instrucciones de asignación y de invocación de método.</span><span class="sxs-lookup"><span data-stu-id="945ff-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="945ff-105">Conversiones de puntero implícitas</span><span class="sxs-lookup"><span data-stu-id="945ff-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="945ff-106">De</span><span class="sxs-lookup"><span data-stu-id="945ff-106">From</span></span>|<span data-ttu-id="945ff-107">Para</span><span class="sxs-lookup"><span data-stu-id="945ff-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="945ff-108">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="945ff-108">Any pointer type</span></span>|<span data-ttu-id="945ff-109">void\*</span><span class="sxs-lookup"><span data-stu-id="945ff-109">void\*</span></span>|  
|<span data-ttu-id="945ff-110">null</span><span class="sxs-lookup"><span data-stu-id="945ff-110">null</span></span>|<span data-ttu-id="945ff-111">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="945ff-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="945ff-112">La conversión de puntero explícita se usa para realizar conversiones, donde no existe ninguna conversión implícita, mediante una expresión de conversión.</span><span class="sxs-lookup"><span data-stu-id="945ff-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="945ff-113">En la siguiente tabla se muestran estas conversiones.</span><span class="sxs-lookup"><span data-stu-id="945ff-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="945ff-114">Conversiones de puntero explícitas</span><span class="sxs-lookup"><span data-stu-id="945ff-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="945ff-115">De</span><span class="sxs-lookup"><span data-stu-id="945ff-115">From</span></span>|<span data-ttu-id="945ff-116">Para</span><span class="sxs-lookup"><span data-stu-id="945ff-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="945ff-117">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="945ff-117">Any pointer type</span></span>|<span data-ttu-id="945ff-118">Cualquier otro tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="945ff-118">Any other pointer type</span></span>|  
|<span data-ttu-id="945ff-119">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="945ff-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="945ff-120">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="945ff-120">Any pointer type</span></span>|  
|<span data-ttu-id="945ff-121">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="945ff-121">Any pointer type</span></span>|<span data-ttu-id="945ff-122">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="945ff-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="945ff-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="945ff-123">Example</span></span>  
 <span data-ttu-id="945ff-124">En el ejemplo siguiente, un puntero a `int` se convierte en un puntero a `byte`.</span><span class="sxs-lookup"><span data-stu-id="945ff-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="945ff-125">Tenga en cuenta que el puntero señala al byte dirigido más bajo de la variable.</span><span class="sxs-lookup"><span data-stu-id="945ff-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="945ff-126">Cuando incrementa el resultado sucesivamente, hasta el tamaño de `int` (4 bytes), puede mostrar los bytes restantes de la variable.</span><span class="sxs-lookup"><span data-stu-id="945ff-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="945ff-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="945ff-127">See also</span></span>

- [<span data-ttu-id="945ff-128">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="945ff-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="945ff-129">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="945ff-129">Pointer types</span></span>](pointer-types.md)
- [<span data-ttu-id="945ff-130">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="945ff-130">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="945ff-131">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="945ff-131">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="945ff-132">unsafe</span><span class="sxs-lookup"><span data-stu-id="945ff-132">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="945ff-133">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="945ff-133">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="945ff-134">stackalloc</span><span class="sxs-lookup"><span data-stu-id="945ff-134">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
