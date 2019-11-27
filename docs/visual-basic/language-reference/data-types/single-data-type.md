---
title: Single (Tipo de datos)
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
ms.openlocfilehash: 60a688c510f6e36dca5809566b37a388429e18c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343915"
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="a3678-102">Single (Tipo de datos, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3678-102">Single Data Type (Visual Basic)</span></span>

<span data-ttu-id="a3678-103">Contiene números de punto flotante de precisión sencilla (4 bytes) de IEEE 32 bits con signo que van en el valor de-3.4028235 E + 38 a-401298e E-45 para los valores negativos y desde 401298e E-45 hasta 3.4028235 E + 38 para los valores positivos.</span><span class="sxs-lookup"><span data-stu-id="a3678-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="a3678-104">Los números de precisión sencilla almacenan una aproximación de un número real.</span><span class="sxs-lookup"><span data-stu-id="a3678-104">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3678-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a3678-105">Remarks</span></span>  

 <span data-ttu-id="a3678-106">Utilice el tipo de datos `Single` para contener valores de punto flotante que no requieran el ancho completo de los datos de `Double`.</span><span class="sxs-lookup"><span data-stu-id="a3678-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="a3678-107">En algunos casos, es posible que el Common Language Runtime pueda empaquetar las variables de `Single` en estrecha colaboración y ahorrar consumo de memoria.</span><span class="sxs-lookup"><span data-stu-id="a3678-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="a3678-108">El valor predeterminado de `Single` es 0.</span><span class="sxs-lookup"><span data-stu-id="a3678-108">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="a3678-109">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="a3678-109">Programming Tips</span></span>  
  
- <span data-ttu-id="a3678-110">**Precisión.**</span><span class="sxs-lookup"><span data-stu-id="a3678-110">**Precision.**</span></span> <span data-ttu-id="a3678-111">Al trabajar con números de punto flotante, tenga en cuenta que no siempre tienen una representación precisa en la memoria.</span><span class="sxs-lookup"><span data-stu-id="a3678-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="a3678-112">Esto podría dar lugar a resultados inesperados de ciertas operaciones, como la comparación de valores y el operador `Mod`.</span><span class="sxs-lookup"><span data-stu-id="a3678-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="a3678-113">Para obtener más información, vea [solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="a3678-113">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
- <span data-ttu-id="a3678-114">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="a3678-114">**Widening.**</span></span> <span data-ttu-id="a3678-115">El tipo de datos `Single` se amplía a `Double`.</span><span class="sxs-lookup"><span data-stu-id="a3678-115">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="a3678-116">Esto significa que puede convertir `Single` a `Double` sin encontrar un error de <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a3678-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="a3678-117">**Ceros a la derecha.**</span><span class="sxs-lookup"><span data-stu-id="a3678-117">**Trailing Zeros.**</span></span> <span data-ttu-id="a3678-118">Los tipos de datos de punto flotante no tienen ninguna representación interna de 0 caracteres finales.</span><span class="sxs-lookup"><span data-stu-id="a3678-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="a3678-119">Por ejemplo, no distinguen entre 4,2000 y 4,2.</span><span class="sxs-lookup"><span data-stu-id="a3678-119">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="a3678-120">Por lo tanto, los caracteres 0 finales no aparecen al mostrar o imprimir valores de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="a3678-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
- <span data-ttu-id="a3678-121">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="a3678-121">**Type Characters.**</span></span> <span data-ttu-id="a3678-122">Al agregar el carácter de tipo literal `F` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Single`.</span><span class="sxs-lookup"><span data-stu-id="a3678-122">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="a3678-123">Si se agrega el carácter de tipo identificador `!` a cualquier identificador, se convierte forzosamente al tipo `Single`.</span><span class="sxs-lookup"><span data-stu-id="a3678-123">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
- <span data-ttu-id="a3678-124">**Tipo de marco.**</span><span class="sxs-lookup"><span data-stu-id="a3678-124">**Framework Type.**</span></span> <span data-ttu-id="a3678-125">El tipo correspondiente en .NET Framework es la estructura <xref:System.Single?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a3678-125">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3678-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3678-126">See also</span></span>

- <xref:System.Single?displayProperty=nameWithType>
- [<span data-ttu-id="a3678-127">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="a3678-127">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="a3678-128">Decimal (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="a3678-128">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [<span data-ttu-id="a3678-129">Double (tipos de datos)</span><span class="sxs-lookup"><span data-stu-id="a3678-129">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="a3678-130">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="a3678-130">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="a3678-131">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="a3678-131">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="a3678-132">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="a3678-132">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="a3678-133">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="a3678-133">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
