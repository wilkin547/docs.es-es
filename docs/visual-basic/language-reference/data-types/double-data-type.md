---
title: Double (Tipo de datos, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 701d10a334757a96ffd634204c1e1d5eb5418ce6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054450"
---
# <a name="double-data-type-visual-basic"></a><span data-ttu-id="8993a-102">Double (Tipo de datos, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8993a-102">Double Data Type (Visual Basic)</span></span>
<span data-ttu-id="8993a-103">Contiene números con signo IEEE de 64 bits (8 bytes) precisión doble punto flotante que intervalo entre - 1, 79769313486231570E + 308 a - 4, 94065645841246544E-324 para los valores negativos y de 4, 94065645841246544E-324 a 1, 79769313486231570E + 308 para valores positivos.</span><span class="sxs-lookup"><span data-stu-id="8993a-103">Holds signed IEEE 64-bit (8-byte) double-precision floating-point numbers that range in value from -1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values and from 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span> <span data-ttu-id="8993a-104">Números de precisión doble almacenan una aproximación de un número real.</span><span class="sxs-lookup"><span data-stu-id="8993a-104">Double-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8993a-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8993a-105">Remarks</span></span>  
 <span data-ttu-id="8993a-106">El `Double` tipo de datos proporciona las magnitudes más grandes y más pequeño posibles para un número.</span><span class="sxs-lookup"><span data-stu-id="8993a-106">The `Double` data type provides the largest and smallest possible magnitudes for a number.</span></span>  
  
 <span data-ttu-id="8993a-107">El valor predeterminado de `Double` es 0.</span><span class="sxs-lookup"><span data-stu-id="8993a-107">The default value of `Double` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="8993a-108">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="8993a-108">Programming Tips</span></span>  
  
- <span data-ttu-id="8993a-109">**Precisión.**</span><span class="sxs-lookup"><span data-stu-id="8993a-109">**Precision.**</span></span> <span data-ttu-id="8993a-110">Cuando se trabaja con números de punto flotante, recuerde que no siempre tienen una representación precisa en memoria.</span><span class="sxs-lookup"><span data-stu-id="8993a-110">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="8993a-111">Esto podría provocar resultados inesperados en ciertas operaciones, como la comparación de valor y el `Mod` operador.</span><span class="sxs-lookup"><span data-stu-id="8993a-111">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="8993a-112">Para obtener más información, consulte [solución de problemas de los tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="8993a-112">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
- <span data-ttu-id="8993a-113">**Ceros finales.**</span><span class="sxs-lookup"><span data-stu-id="8993a-113">**Trailing Zeros.**</span></span> <span data-ttu-id="8993a-114">Los tipos de datos de punto flotante no tienen una representación interna de cero caracteres finales.</span><span class="sxs-lookup"><span data-stu-id="8993a-114">The floating-point data types do not have any internal representation of trailing zero characters.</span></span> <span data-ttu-id="8993a-115">Por ejemplo, no distinguen entre 4,2000 y 4,2.</span><span class="sxs-lookup"><span data-stu-id="8993a-115">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="8993a-116">Por lo tanto, cero caracteres finales no aparecen cuando se muestren o valores de punto flotante de impresión.</span><span class="sxs-lookup"><span data-stu-id="8993a-116">Consequently, trailing zero characters do not appear when you display or print floating-point values.</span></span>  
  
- <span data-ttu-id="8993a-117">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="8993a-117">**Type Characters.**</span></span> <span data-ttu-id="8993a-118">Al agregar el carácter de tipo literal `R` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Double`.</span><span class="sxs-lookup"><span data-stu-id="8993a-118">Appending the literal type character `R` to a literal forces it to the `Double` data type.</span></span> <span data-ttu-id="8993a-119">Por ejemplo, si un valor entero seguido `R`, el valor se cambia a un `Double`.</span><span class="sxs-lookup"><span data-stu-id="8993a-119">For example, if an integer value is followed by `R`, the value is changed to a `Double`.</span></span>  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     <span data-ttu-id="8993a-120">Si se agrega el carácter de tipo identificador `#` a cualquier identificador, se convierte forzosamente al tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="8993a-120">Appending the identifier type character `#` to any identifier forces it to `Double`.</span></span> <span data-ttu-id="8993a-121">En el ejemplo siguiente, la variable `num` se escribe como un `Double`:</span><span class="sxs-lookup"><span data-stu-id="8993a-121">In the following example, the variable `num` is typed as a `Double`:</span></span>  
  
    ```  
    Dim num# = 3  
    ```  
  
- <span data-ttu-id="8993a-122">**Tipo de marco de trabajo.**</span><span class="sxs-lookup"><span data-stu-id="8993a-122">**Framework Type.**</span></span> <span data-ttu-id="8993a-123">El tipo correspondiente en .NET Framework es la estructura <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8993a-123">The corresponding type in the .NET Framework is the <xref:System.Double?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8993a-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="8993a-124">See also</span></span>

- <xref:System.Double?displayProperty=nameWithType>
- [<span data-ttu-id="8993a-125">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="8993a-125">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="8993a-126">Decimal (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="8993a-126">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [<span data-ttu-id="8993a-127">Single (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="8993a-127">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="8993a-128">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="8993a-128">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="8993a-129">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="8993a-129">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="8993a-130">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="8993a-130">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="8993a-131">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="8993a-131">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="8993a-132">Caracteres de tipo</span><span class="sxs-lookup"><span data-stu-id="8993a-132">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
