---
title: Single (Tipo de datos, Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Single
helpviewer_keywords:
- Single data type
- F literal type character [Visual Basic]
- trailing zeros
- real numbers
- literal type characters [Visual Basic], F
- trailing 0 characters [Visual Basic]
- identifier type characters [Visual Basic], !
- single-precision numbers
- '! identifier type character'
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- floating-point numbers [Visual Basic], Single data type
- numbers [Visual Basic], real
- zeros, trailing
- numbers [Visual Basic], floating point
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c91dbdf73ed1e26393518001ec8651557e5b780f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="b19c3-102">Single (Tipo de datos, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b19c3-102">Single Data Type (Visual Basic)</span></span>
<span data-ttu-id="b19c3-103">Contiene con signo números de punto flotante IEEE 32 bits (4 bytes) precisión sencilla que abarcan un valor de - 3, 4028235E + 38 a - 1, 401298E-45 para los valores negativos y entre 1, 401298E-45 a 3, 4028235E + 38 para valores positivos.</span><span class="sxs-lookup"><span data-stu-id="b19c3-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="b19c3-104">Los números de precisión sencilla almacenan una aproximación de un número real.</span><span class="sxs-lookup"><span data-stu-id="b19c3-104">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b19c3-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b19c3-105">Remarks</span></span>  
 <span data-ttu-id="b19c3-106">Use la `Single` tipo de datos para contener valores de punto flotante que no requieren el ancho completo de datos de `Double`.</span><span class="sxs-lookup"><span data-stu-id="b19c3-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="b19c3-107">En algunos casos, common language runtime podrían llevar empaquetar su `Single` variables estrecha colaboración y ahorre consumo de memoria.</span><span class="sxs-lookup"><span data-stu-id="b19c3-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="b19c3-108">El valor predeterminado de `Single` es 0.</span><span class="sxs-lookup"><span data-stu-id="b19c3-108">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="b19c3-109">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="b19c3-109">Programming Tips</span></span>  
  
-   <span data-ttu-id="b19c3-110">**Precisión.**</span><span class="sxs-lookup"><span data-stu-id="b19c3-110">**Precision.**</span></span> <span data-ttu-id="b19c3-111">Cuando trabaje con números de punto flotante, tenga en cuenta que no siempre tienen una representación precisa en memoria.</span><span class="sxs-lookup"><span data-stu-id="b19c3-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="b19c3-112">Esto podría provocar resultados inesperados en ciertas operaciones, como comparación de valores y la `Mod` operador.</span><span class="sxs-lookup"><span data-stu-id="b19c3-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="b19c3-113">Para obtener más información, consulte [solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="b19c3-113">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
-   <span data-ttu-id="b19c3-114">**De ampliación.**</span><span class="sxs-lookup"><span data-stu-id="b19c3-114">**Widening.**</span></span> <span data-ttu-id="b19c3-115">El `Single` tipo de datos se amplía a `Double`.</span><span class="sxs-lookup"><span data-stu-id="b19c3-115">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="b19c3-116">Esto significa que se puede convertir `Single` a `Double` sin que se produzca una <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="b19c3-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="b19c3-117">**Ceros finales.**</span><span class="sxs-lookup"><span data-stu-id="b19c3-117">**Trailing Zeros.**</span></span> <span data-ttu-id="b19c3-118">Los tipos de datos de punto flotante no tiene una representación interna de caracteres 0 finales.</span><span class="sxs-lookup"><span data-stu-id="b19c3-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="b19c3-119">Por ejemplo, no distinguen entre 4,2000 y 4,2.</span><span class="sxs-lookup"><span data-stu-id="b19c3-119">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="b19c3-120">Por lo tanto, los caracteres 0 finales no aparecen al mostrar o imprimir valores de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="b19c3-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
-   <span data-ttu-id="b19c3-121">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="b19c3-121">**Type Characters.**</span></span> <span data-ttu-id="b19c3-122">Al agregar el carácter de tipo literal `F` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Single`.</span><span class="sxs-lookup"><span data-stu-id="b19c3-122">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="b19c3-123">Si se agrega el carácter de tipo identificador `!` a cualquier identificador, se convierte forzosamente al tipo `Single`.</span><span class="sxs-lookup"><span data-stu-id="b19c3-123">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
-   <span data-ttu-id="b19c3-124">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="b19c3-124">**Framework Type.**</span></span> <span data-ttu-id="b19c3-125">El tipo correspondiente en .NET Framework es la estructura <xref:System.Single?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b19c3-125">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b19c3-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="b19c3-126">See Also</span></span>  
 <xref:System.Single?displayProperty=nameWithType>  
 [<span data-ttu-id="b19c3-127">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="b19c3-127">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="b19c3-128">Decimal (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="b19c3-128">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [<span data-ttu-id="b19c3-129">Double (tipos de datos)</span><span class="sxs-lookup"><span data-stu-id="b19c3-129">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [<span data-ttu-id="b19c3-130">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="b19c3-130">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="b19c3-131">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="b19c3-131">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="b19c3-132">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="b19c3-132">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="b19c3-133">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="b19c3-133">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
