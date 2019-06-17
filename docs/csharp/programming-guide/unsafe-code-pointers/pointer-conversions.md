---
title: 'Conversiones de puntero: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 3cef2f2d2af2d285504daea14aa57c55b9e9a21b
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833460"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="9d9ea-102">Conversiones de puntero (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9d9ea-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="9d9ea-103">En la tabla siguiente se muestran las conversiones de puntero implícitas predefinidas.</span><span class="sxs-lookup"><span data-stu-id="9d9ea-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="9d9ea-104">Las conversiones implícitas pueden ocurrir en muchas situaciones, incluidas las instrucciones de asignación y de invocación de método.</span><span class="sxs-lookup"><span data-stu-id="9d9ea-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="9d9ea-105">Conversiones de puntero implícitas</span><span class="sxs-lookup"><span data-stu-id="9d9ea-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="9d9ea-106">De</span><span class="sxs-lookup"><span data-stu-id="9d9ea-106">From</span></span>|<span data-ttu-id="9d9ea-107">En</span><span class="sxs-lookup"><span data-stu-id="9d9ea-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="9d9ea-108">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="9d9ea-108">Any pointer type</span></span>|<span data-ttu-id="9d9ea-109">void\*</span><span class="sxs-lookup"><span data-stu-id="9d9ea-109">void\*</span></span>|  
|<span data-ttu-id="9d9ea-110">nulo</span><span class="sxs-lookup"><span data-stu-id="9d9ea-110">null</span></span>|<span data-ttu-id="9d9ea-111">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="9d9ea-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="9d9ea-112">La conversión de puntero explícita se usa para realizar conversiones, donde no existe ninguna conversión implícita, mediante una expresión de conversión.</span><span class="sxs-lookup"><span data-stu-id="9d9ea-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="9d9ea-113">En la siguiente tabla se muestran estas conversiones.</span><span class="sxs-lookup"><span data-stu-id="9d9ea-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="9d9ea-114">Conversiones de puntero explícitas</span><span class="sxs-lookup"><span data-stu-id="9d9ea-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="9d9ea-115">De</span><span class="sxs-lookup"><span data-stu-id="9d9ea-115">From</span></span>|<span data-ttu-id="9d9ea-116">En</span><span class="sxs-lookup"><span data-stu-id="9d9ea-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="9d9ea-117">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="9d9ea-117">Any pointer type</span></span>|<span data-ttu-id="9d9ea-118">Cualquier otro tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="9d9ea-118">Any other pointer type</span></span>|  
|<span data-ttu-id="9d9ea-119">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="9d9ea-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="9d9ea-120">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="9d9ea-120">Any pointer type</span></span>|  
|<span data-ttu-id="9d9ea-121">Cualquier tipo de puntero</span><span class="sxs-lookup"><span data-stu-id="9d9ea-121">Any pointer type</span></span>|<span data-ttu-id="9d9ea-122">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="9d9ea-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9d9ea-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9d9ea-123">Example</span></span>  
 <span data-ttu-id="9d9ea-124">En el ejemplo siguiente, un puntero a `int` se convierte en un puntero a `byte`.</span><span class="sxs-lookup"><span data-stu-id="9d9ea-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="9d9ea-125">Tenga en cuenta que el puntero señala al byte dirigido más bajo de la variable.</span><span class="sxs-lookup"><span data-stu-id="9d9ea-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="9d9ea-126">Cuando incrementa el resultado sucesivamente, hasta el tamaño de `int` (4 bytes), puede mostrar los bytes restantes de la variable.</span><span class="sxs-lookup"><span data-stu-id="9d9ea-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="9d9ea-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d9ea-127">See also</span></span>

- [<span data-ttu-id="9d9ea-128">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9d9ea-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="9d9ea-129">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="9d9ea-129">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="9d9ea-130">Tipos</span><span class="sxs-lookup"><span data-stu-id="9d9ea-130">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="9d9ea-131">unsafe</span><span class="sxs-lookup"><span data-stu-id="9d9ea-131">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="9d9ea-132">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="9d9ea-132">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="9d9ea-133">stackalloc</span><span class="sxs-lookup"><span data-stu-id="9d9ea-133">stackalloc</span></span>](../../../csharp/language-reference/operators/stackalloc.md)
