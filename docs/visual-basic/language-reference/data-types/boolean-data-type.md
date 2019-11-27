---
title: Tipo de datos booleano
ms.date: 07/20/2015
f1_keywords:
- vb.FALSE
- vb.TRUE
- vb.Boolean
helpviewer_keywords:
- Boolean data type
- Boolean values [Visual Basic], False keyword
- False keyword [Visual Basic]
- True keyword [Visual Basic]
- Boolean values [Visual Basic], True keyword
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
ms.openlocfilehash: 5d05514207c5d07e81aab897f40f728570f6bd87
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347846"
---
# <a name="boolean-data-type-visual-basic"></a><span data-ttu-id="365c1-102">Boolean (Tipo de datos, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="365c1-102">Boolean Data Type (Visual Basic)</span></span>

<span data-ttu-id="365c1-103">Contiene valores que solo pueden ser `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="365c1-103">Holds values that can be only `True` or `False`.</span></span> <span data-ttu-id="365c1-104">Las palabras clave `True` y `False` corresponden a los dos Estados de las variables `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="365c1-104">The keywords `True` and `False` correspond to the two states of `Boolean` variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="365c1-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="365c1-105">Remarks</span></span>  

 <span data-ttu-id="365c1-106">Utilice el [tipo de datos booleano (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) para contener valores de dos Estados como true/false, yes/no o ON/OFF.</span><span class="sxs-lookup"><span data-stu-id="365c1-106">Use the [Boolean Data Type (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) to contain two-state values such as true/false, yes/no, or on/off.</span></span>  
  
 <span data-ttu-id="365c1-107">El valor predeterminado de `Boolean` es `False`.</span><span class="sxs-lookup"><span data-stu-id="365c1-107">The default value of `Boolean` is `False`.</span></span>  
  
 <span data-ttu-id="365c1-108">`Boolean` valores no se almacenan como números y los valores almacenados no están diseñados para ser equivalentes a números.</span><span class="sxs-lookup"><span data-stu-id="365c1-108">`Boolean` values are not stored as numbers, and the stored values are not intended to be equivalent to numbers.</span></span> <span data-ttu-id="365c1-109">Nunca debe escribir código que se base en valores numéricos equivalentes para `True` y `False`.</span><span class="sxs-lookup"><span data-stu-id="365c1-109">You should never write code that relies on equivalent numeric values for `True` and `False`.</span></span> <span data-ttu-id="365c1-110">Siempre que sea posible, debe restringir el uso de `Boolean` variables a los valores lógicos para los que están diseñadas.</span><span class="sxs-lookup"><span data-stu-id="365c1-110">Whenever possible, you should restrict usage of `Boolean` variables to the logical values for which they are designed.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="365c1-111">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="365c1-111">Type Conversions</span></span>  

 <span data-ttu-id="365c1-112">Cuando Visual Basic convierte valores de tipos de datos numéricos en `Boolean`, 0 se convierte en `False` y todos los demás valores se `True`.</span><span class="sxs-lookup"><span data-stu-id="365c1-112">When Visual Basic converts numeric data type values to `Boolean`, 0 becomes `False` and all other values become `True`.</span></span> <span data-ttu-id="365c1-113">Cuando Visual Basic convierte `Boolean` valores en tipos numéricos, `False` se convierte en 0 y `True` se convierte en-1.</span><span class="sxs-lookup"><span data-stu-id="365c1-113">When Visual Basic converts `Boolean` values to numeric types, `False` becomes 0 and `True` becomes -1.</span></span>  
  
 <span data-ttu-id="365c1-114">Al convertir entre `Boolean` valores y tipos de datos numéricos, tenga en cuenta que los métodos de conversión .NET Framework no siempre producen los mismos resultados que las palabras clave de conversión Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="365c1-114">When you convert between `Boolean` values and numeric data types, keep in mind that the .NET Framework conversion methods do not always produce the same results as the Visual Basic conversion keywords.</span></span> <span data-ttu-id="365c1-115">Esto se debe a que la conversión de Visual Basic conserva el comportamiento compatible con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="365c1-115">This is because the Visual Basic conversion retains behavior compatible with previous versions.</span></span> <span data-ttu-id="365c1-116">Para obtener más información, vea el tema sobre el tipo Boolean no se convierte a un tipo numérico con precisión en los [tipos de datos de solución de problemas](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="365c1-116">For more information, see "Boolean Type Does Not Convert to Numeric Type Accurately" in [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="365c1-117">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="365c1-117">Programming Tips</span></span>  
  
- <span data-ttu-id="365c1-118">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="365c1-118">**Negative Numbers.**</span></span> <span data-ttu-id="365c1-119">`Boolean` no es un tipo numérico y no puede representar un valor negativo.</span><span class="sxs-lookup"><span data-stu-id="365c1-119">`Boolean` is not a numeric type and cannot represent a negative value.</span></span> <span data-ttu-id="365c1-120">En cualquier caso, no debe utilizar `Boolean` para contener valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="365c1-120">In any case, you should not use `Boolean` to hold numeric values.</span></span>  
  
- <span data-ttu-id="365c1-121">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="365c1-121">**Type Characters.**</span></span> <span data-ttu-id="365c1-122">`Boolean` no tiene un carácter de tipo literal o un carácter de tipo de identificador.</span><span class="sxs-lookup"><span data-stu-id="365c1-122">`Boolean` has no literal type character or identifier type character.</span></span>  
  
- <span data-ttu-id="365c1-123">**Tipo de marco.**</span><span class="sxs-lookup"><span data-stu-id="365c1-123">**Framework Type.**</span></span> <span data-ttu-id="365c1-124">El tipo correspondiente en .NET Framework es la estructura <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="365c1-124">The corresponding type in the .NET Framework is the <xref:System.Boolean?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="365c1-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="365c1-125">Example</span></span>  

 <span data-ttu-id="365c1-126">En el ejemplo siguiente, `runningVB` es una variable de `Boolean`, que almacena un valor de sí/no simple.</span><span class="sxs-lookup"><span data-stu-id="365c1-126">In the following example, `runningVB` is a `Boolean` variable, which stores a simple yes/no setting.</span></span>  
  
```vb  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="365c1-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="365c1-127">See also</span></span>

- <xref:System.Boolean?displayProperty=nameWithType>
- [<span data-ttu-id="365c1-128">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="365c1-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="365c1-129">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="365c1-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="365c1-130">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="365c1-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="365c1-131">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="365c1-131">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="365c1-132">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="365c1-132">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="365c1-133">Función CType</span><span class="sxs-lookup"><span data-stu-id="365c1-133">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
