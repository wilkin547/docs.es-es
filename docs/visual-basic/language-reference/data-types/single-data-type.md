---
description: 'Más información acerca de: tipo de datos único (Visual Basic)'
title: Tipo de datos Single
ms.date: 07/20/2015
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
ms.openlocfilehash: f30e21d3b2d2960a040609a9422ec71cc029f5be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792133"
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="5384e-103">Single (Tipo de datos, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5384e-103">Single Data Type (Visual Basic)</span></span>

<span data-ttu-id="5384e-104">Contiene números de punto flotante de precisión sencilla (4 bytes) de IEEE 32 bits con signo que van en el valor de-3.4028235 E + 38 a-401298e E-45 para los valores negativos y desde 401298e E-45 hasta 3.4028235 E + 38 para los valores positivos.</span><span class="sxs-lookup"><span data-stu-id="5384e-104">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="5384e-105">Los números de precisión sencilla almacenan una aproximación de un número real.</span><span class="sxs-lookup"><span data-stu-id="5384e-105">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5384e-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5384e-106">Remarks</span></span>  

 <span data-ttu-id="5384e-107">Utilice el `Single` tipo de datos para contener valores de punto flotante que no requieran el ancho completo de los datos de `Double` .</span><span class="sxs-lookup"><span data-stu-id="5384e-107">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="5384e-108">En algunos casos, es posible que el Common Language Runtime pueda empaquetar las `Single` variables en estrecha colaboración y ahorrar consumo de memoria.</span><span class="sxs-lookup"><span data-stu-id="5384e-108">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="5384e-109">El valor predeterminado de `Single` es 0.</span><span class="sxs-lookup"><span data-stu-id="5384e-109">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="5384e-110">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="5384e-110">Programming Tips</span></span>  
  
- <span data-ttu-id="5384e-111">**Precisión.**</span><span class="sxs-lookup"><span data-stu-id="5384e-111">**Precision.**</span></span> <span data-ttu-id="5384e-112">Al trabajar con números de punto flotante, tenga en cuenta que no siempre tienen una representación precisa en la memoria.</span><span class="sxs-lookup"><span data-stu-id="5384e-112">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="5384e-113">Esto podría dar lugar a resultados inesperados de ciertas operaciones, como la comparación de valores y el `Mod` operador.</span><span class="sxs-lookup"><span data-stu-id="5384e-113">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="5384e-114">Para obtener más información, vea [solución de problemas de tipos de datos](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="5384e-114">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
- <span data-ttu-id="5384e-115">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="5384e-115">**Widening.**</span></span> <span data-ttu-id="5384e-116">El `Single` tipo de datos se amplía a `Double` .</span><span class="sxs-lookup"><span data-stu-id="5384e-116">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="5384e-117">Esto significa que puede convertir `Single` en `Double` sin que se produzca un <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="5384e-117">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="5384e-118">**Ceros a la derecha.**</span><span class="sxs-lookup"><span data-stu-id="5384e-118">**Trailing Zeros.**</span></span> <span data-ttu-id="5384e-119">Los tipos de datos de punto flotante no tienen ninguna representación interna de 0 caracteres finales.</span><span class="sxs-lookup"><span data-stu-id="5384e-119">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="5384e-120">Por ejemplo, no distinguen entre 4,2000 y 4,2.</span><span class="sxs-lookup"><span data-stu-id="5384e-120">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="5384e-121">Por lo tanto, los caracteres 0 finales no aparecen al mostrar o imprimir valores de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="5384e-121">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
- <span data-ttu-id="5384e-122">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="5384e-122">**Type Characters.**</span></span> <span data-ttu-id="5384e-123">Al agregar el carácter de tipo literal `F` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Single`.</span><span class="sxs-lookup"><span data-stu-id="5384e-123">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="5384e-124">Si se agrega el carácter de tipo identificador `!` a cualquier identificador, se convierte forzosamente al tipo `Single`.</span><span class="sxs-lookup"><span data-stu-id="5384e-124">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
- <span data-ttu-id="5384e-125">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="5384e-125">**Framework Type.**</span></span> <span data-ttu-id="5384e-126">El tipo correspondiente en .NET Framework es la estructura <xref:System.Single?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5384e-126">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5384e-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="5384e-127">See also</span></span>

- <xref:System.Single?displayProperty=nameWithType>
- [<span data-ttu-id="5384e-128">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="5384e-128">Data Types</span></span>](index.md)
- [<span data-ttu-id="5384e-129">Tipo de datos Decimal</span><span class="sxs-lookup"><span data-stu-id="5384e-129">Decimal Data Type</span></span>](decimal-data-type.md)
- [<span data-ttu-id="5384e-130">Tipo de datos Double</span><span class="sxs-lookup"><span data-stu-id="5384e-130">Double Data Type</span></span>](double-data-type.md)
- [<span data-ttu-id="5384e-131">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="5384e-131">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="5384e-132">Resumen de las conversiones</span><span class="sxs-lookup"><span data-stu-id="5384e-132">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="5384e-133">Uso eficiente de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="5384e-133">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="5384e-134">Solución de problemas de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="5384e-134">Troubleshooting Data Types</span></span>](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
