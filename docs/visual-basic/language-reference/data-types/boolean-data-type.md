---
description: 'Más información acerca de: tipo de datos booleano (Visual Basic)'
title: Tipo de datos Boolean
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
ms.openlocfilehash: cdda6bc0571eb0a2a9ee6a079ffd276bfc89a9b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731414"
---
# <a name="boolean-data-type-visual-basic"></a><span data-ttu-id="14aef-103">Boolean (Tipo de datos, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14aef-103">Boolean Data Type (Visual Basic)</span></span>

<span data-ttu-id="14aef-104">Contiene valores que solo pueden ser `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="14aef-104">Holds values that can be only `True` or `False`.</span></span> <span data-ttu-id="14aef-105">Las palabras clave `True` y `False` se corresponden con los dos Estados de `Boolean` las variables.</span><span class="sxs-lookup"><span data-stu-id="14aef-105">The keywords `True` and `False` correspond to the two states of `Boolean` variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14aef-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="14aef-106">Remarks</span></span>  

 <span data-ttu-id="14aef-107">Utilice el [tipo de datos booleano (Visual Basic)](boolean-data-type.md) para contener valores de dos Estados como true/false, yes/no o ON/OFF.</span><span class="sxs-lookup"><span data-stu-id="14aef-107">Use the [Boolean Data Type (Visual Basic)](boolean-data-type.md) to contain two-state values such as true/false, yes/no, or on/off.</span></span>  
  
 <span data-ttu-id="14aef-108">El valor predeterminado de `Boolean` es `False`.</span><span class="sxs-lookup"><span data-stu-id="14aef-108">The default value of `Boolean` is `False`.</span></span>  
  
 <span data-ttu-id="14aef-109">`Boolean` los valores no se almacenan como números y los valores almacenados no están diseñados para ser equivalentes a números.</span><span class="sxs-lookup"><span data-stu-id="14aef-109">`Boolean` values are not stored as numbers, and the stored values are not intended to be equivalent to numbers.</span></span> <span data-ttu-id="14aef-110">Nunca debe escribir código que se base en valores numéricos equivalentes para `True` y `False` .</span><span class="sxs-lookup"><span data-stu-id="14aef-110">You should never write code that relies on equivalent numeric values for `True` and `False`.</span></span> <span data-ttu-id="14aef-111">Siempre que sea posible, debe restringir `Boolean` el uso de variables a los valores lógicos para los que están diseñadas.</span><span class="sxs-lookup"><span data-stu-id="14aef-111">Whenever possible, you should restrict usage of `Boolean` variables to the logical values for which they are designed.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="14aef-112">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="14aef-112">Type Conversions</span></span>  

 <span data-ttu-id="14aef-113">Cuando Visual Basic convierte valores de tipos de datos numéricos en `Boolean` , 0 se convierte en `False` y todos los demás valores se convierten en `True` .</span><span class="sxs-lookup"><span data-stu-id="14aef-113">When Visual Basic converts numeric data type values to `Boolean`, 0 becomes `False` and all other values become `True`.</span></span> <span data-ttu-id="14aef-114">Cuando Visual Basic convierte `Boolean` valores en tipos numéricos, `False` se convierte en 0 y `True` se convierte en-1.</span><span class="sxs-lookup"><span data-stu-id="14aef-114">When Visual Basic converts `Boolean` values to numeric types, `False` becomes 0 and `True` becomes -1.</span></span>  
  
 <span data-ttu-id="14aef-115">Al convertir entre `Boolean` valores y tipos de datos numéricos, tenga en cuenta que los métodos de conversión .NET Framework no siempre generan los mismos resultados que las palabras clave de conversión Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="14aef-115">When you convert between `Boolean` values and numeric data types, keep in mind that the .NET Framework conversion methods do not always produce the same results as the Visual Basic conversion keywords.</span></span> <span data-ttu-id="14aef-116">Esto se debe a que la conversión de Visual Basic conserva el comportamiento compatible con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="14aef-116">This is because the Visual Basic conversion retains behavior compatible with previous versions.</span></span> <span data-ttu-id="14aef-117">Para obtener más información, vea el tema sobre el tipo Boolean no se convierte a un tipo numérico con precisión en los [tipos de datos de solución de problemas](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="14aef-117">For more information, see "Boolean Type Does Not Convert to Numeric Type Accurately" in [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="14aef-118">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="14aef-118">Programming Tips</span></span>  
  
- <span data-ttu-id="14aef-119">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="14aef-119">**Negative Numbers.**</span></span> <span data-ttu-id="14aef-120">`Boolean` no es un tipo numérico y no puede representar un valor negativo.</span><span class="sxs-lookup"><span data-stu-id="14aef-120">`Boolean` is not a numeric type and cannot represent a negative value.</span></span> <span data-ttu-id="14aef-121">En cualquier caso, no debe usar `Boolean` para contener valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="14aef-121">In any case, you should not use `Boolean` to hold numeric values.</span></span>  
  
- <span data-ttu-id="14aef-122">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="14aef-122">**Type Characters.**</span></span> <span data-ttu-id="14aef-123">`Boolean` no tiene un carácter de tipo literal o un carácter de tipo de identificador.</span><span class="sxs-lookup"><span data-stu-id="14aef-123">`Boolean` has no literal type character or identifier type character.</span></span>  
  
- <span data-ttu-id="14aef-124">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="14aef-124">**Framework Type.**</span></span> <span data-ttu-id="14aef-125">El tipo correspondiente en .NET Framework es la estructura <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="14aef-125">The corresponding type in the .NET Framework is the <xref:System.Boolean?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14aef-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14aef-126">Example</span></span>  

 <span data-ttu-id="14aef-127">En el ejemplo siguiente, `runningVB` es una `Boolean` variable, que almacena un valor sí/no sencillo.</span><span class="sxs-lookup"><span data-stu-id="14aef-127">In the following example, `runningVB` is a `Boolean` variable, which stores a simple yes/no setting.</span></span>  
  
```vb  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="14aef-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="14aef-128">See also</span></span>

- <xref:System.Boolean?displayProperty=nameWithType>
- [<span data-ttu-id="14aef-129">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="14aef-129">Data Types</span></span>](index.md)
- [<span data-ttu-id="14aef-130">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="14aef-130">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="14aef-131">Resumen de las conversiones</span><span class="sxs-lookup"><span data-stu-id="14aef-131">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="14aef-132">Uso eficiente de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="14aef-132">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="14aef-133">Solución de problemas de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="14aef-133">Troubleshooting Data Types</span></span>](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="14aef-134">CType Function</span><span class="sxs-lookup"><span data-stu-id="14aef-134">CType Function</span></span>](../functions/ctype-function.md)
