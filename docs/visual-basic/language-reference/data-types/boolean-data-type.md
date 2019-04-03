---
title: Boolean (Tipo de datos, Visual Basic)
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
ms.openlocfilehash: 7b64302d801a08f976de0ec969983c821f7a8471
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841229"
---
# <a name="boolean-data-type-visual-basic"></a><span data-ttu-id="09187-102">Boolean (Tipo de datos, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09187-102">Boolean Data Type (Visual Basic)</span></span>
<span data-ttu-id="09187-103">Contiene valores que solo pueden ser `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="09187-103">Holds values that can be only `True` or `False`.</span></span> <span data-ttu-id="09187-104">Las palabras clave `True` y `False` corresponden a los dos Estados de `Boolean` variables.</span><span class="sxs-lookup"><span data-stu-id="09187-104">The keywords `True` and `False` correspond to the two states of `Boolean` variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09187-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="09187-105">Remarks</span></span>  
 <span data-ttu-id="09187-106">Use la [(Visual Basic) de tipo de datos Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) para contener valores de dos estados como verdadero/falso, sí/no o activado/desactivado.</span><span class="sxs-lookup"><span data-stu-id="09187-106">Use the [Boolean Data Type (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) to contain two-state values such as true/false, yes/no, or on/off.</span></span>  
  
 <span data-ttu-id="09187-107">El valor predeterminado de `Boolean` es `False`.</span><span class="sxs-lookup"><span data-stu-id="09187-107">The default value of `Boolean` is `False`.</span></span>  
  
 <span data-ttu-id="09187-108">`Boolean` los valores no se almacenan como números y los valores almacenados no pretende ser equivalente a números.</span><span class="sxs-lookup"><span data-stu-id="09187-108">`Boolean` values are not stored as numbers, and the stored values are not intended to be equivalent to numbers.</span></span> <span data-ttu-id="09187-109">Nunca debería escribir código que se basa en valores numéricos equivalentes para `True` y `False`.</span><span class="sxs-lookup"><span data-stu-id="09187-109">You should never write code that relies on equivalent numeric values for `True` and `False`.</span></span> <span data-ttu-id="09187-110">Siempre que sea posible, debe restringir el uso de `Boolean` variables a los valores lógicos para que se han diseñado.</span><span class="sxs-lookup"><span data-stu-id="09187-110">Whenever possible, you should restrict usage of `Boolean` variables to the logical values for which they are designed.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="09187-111">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="09187-111">Type Conversions</span></span>  
 <span data-ttu-id="09187-112">Cuando Visual Basic convierte los valores de tipo de datos numéricos para `Boolean`, se convierte en 0 `False` y todos los demás valores se convierten en `True`.</span><span class="sxs-lookup"><span data-stu-id="09187-112">When Visual Basic converts numeric data type values to `Boolean`, 0 becomes `False` and all other values become `True`.</span></span> <span data-ttu-id="09187-113">Cuando Visual Basic convierte `Boolean` valores a tipos numéricos, `False` se convierte en 0 y `True` se convierte en -1.</span><span class="sxs-lookup"><span data-stu-id="09187-113">When Visual Basic converts `Boolean` values to numeric types, `False` becomes 0 and `True` becomes -1.</span></span>  
  
 <span data-ttu-id="09187-114">Al convertir entre `Boolean` valores y tipos de datos numéricos, tenga en cuenta que los métodos de conversión de .NET Framework no siempre producen los mismos resultados que las palabras clave de conversión de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="09187-114">When you convert between `Boolean` values and numeric data types, keep in mind that the .NET Framework conversion methods do not always produce the same results as the Visual Basic conversion keywords.</span></span> <span data-ttu-id="09187-115">Esto es porque la conversión de Visual Basic conserva un comportamiento compatible con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="09187-115">This is because the Visual Basic conversion retains behavior compatible with previous versions.</span></span> <span data-ttu-id="09187-116">Para obtener más información, vea "Booleano tipo Does no convertir al tipo numérico correctamente" en [solución de problemas de los tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="09187-116">For more information, see "Boolean Type Does Not Convert to Numeric Type Accurately" in [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="09187-117">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="09187-117">Programming Tips</span></span>  
  
-   <span data-ttu-id="09187-118">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="09187-118">**Negative Numbers.**</span></span> <span data-ttu-id="09187-119">`Boolean` no es un tipo numérico y no puede representar un valor negativo.</span><span class="sxs-lookup"><span data-stu-id="09187-119">`Boolean` is not a numeric type and cannot represent a negative value.</span></span> <span data-ttu-id="09187-120">En cualquier caso, no debe utilizar `Boolean` para contener valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="09187-120">In any case, you should not use `Boolean` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="09187-121">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="09187-121">**Type Characters.**</span></span> <span data-ttu-id="09187-122">`Boolean` no tiene ningún carácter de tipo literal o un carácter de tipo identificador.</span><span class="sxs-lookup"><span data-stu-id="09187-122">`Boolean` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="09187-123">**Tipo de marco de trabajo.**</span><span class="sxs-lookup"><span data-stu-id="09187-123">**Framework Type.**</span></span> <span data-ttu-id="09187-124">El tipo correspondiente en .NET Framework es la estructura <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="09187-124">The corresponding type in the .NET Framework is the <xref:System.Boolean?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09187-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09187-125">Example</span></span>  
 <span data-ttu-id="09187-126">En el ejemplo siguiente, `runningVB` es un `Boolean` variable, que almacena un sí/no.</span><span class="sxs-lookup"><span data-stu-id="09187-126">In the following example, `runningVB` is a `Boolean` variable, which stores a simple yes/no setting.</span></span>  
  
```  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="09187-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="09187-127">See also</span></span>

- <xref:System.Boolean?displayProperty=nameWithType>
- [<span data-ttu-id="09187-128">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="09187-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="09187-129">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="09187-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="09187-130">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="09187-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="09187-131">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="09187-131">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="09187-132">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="09187-132">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="09187-133">Función CType</span><span class="sxs-lookup"><span data-stu-id="09187-133">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
