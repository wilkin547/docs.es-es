---
title: Long (Tipo de datos, Visual Basic)
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1e21ed43ddc6efb018df0581faed1ebf270ab3ca
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="long-data-type-visual-basic"></a><span data-ttu-id="8366b-102">Tipo de datos Long (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8366b-102">Long data type (Visual Basic)</span></span>

<span data-ttu-id="8366b-103">Contiene enteros de 64 bits (8 bytes) cuyo valor oscila -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807 con signo (9.2 … E + 18).</span><span class="sxs-lookup"><span data-stu-id="8366b-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8366b-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8366b-104">Remarks</span></span>

 <span data-ttu-id="8366b-105">Use la `Long` tipo de datos para que contenga números enteros que son demasiado grandes para caber la `Integer` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="8366b-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span></span>  
  
 <span data-ttu-id="8366b-106">El valor predeterminado de `Long` es 0.</span><span class="sxs-lookup"><span data-stu-id="8366b-106">The default value of `Long` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="8366b-107">Asignaciones de literales</span><span class="sxs-lookup"><span data-stu-id="8366b-107">Literal assignments</span></span> 

<span data-ttu-id="8366b-108">Puede declarar e inicializar un `Long` variable asignarle un decimal literal, un literal hexadecimal, un literal octal, o (a partir de Visual Basic de 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="8366b-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="8366b-109">Si el literal entero está fuera del intervalo de `Long` (es decir, si es inferior a <xref:System.Int64.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Int64.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="8366b-109">If the integer literal is outside the range of `Long` (that is, if it is less than <xref:System.Int64.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="8366b-110">En el ejemplo siguiente, los enteros que equivalen a 4 294 967 296 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `Long`.</span><span class="sxs-lookup"><span data-stu-id="8366b-110">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `Long` values.</span></span>
  
[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]  

> [!NOTE]
> <span data-ttu-id="8366b-111">Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="8366b-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="8366b-112">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="8366b-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="8366b-113">A partir de Visual Basic de 2017, también puede utilizar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como en el ejemplo siguiente se muestra.</span><span class="sxs-lookup"><span data-stu-id="8366b-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="8366b-114">También pueden incluir literales numéricos el `L` [escriba carácter](../../programming-guide\language-features\data-types/type-characters.md) para denotar el `Long` tipo de datos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="8366b-114">Numeric literals can also include the `L` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span></span>

```vb
Dim number = &H0FAC0326L
```

## <a name="programming-tips"></a><span data-ttu-id="8366b-115">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="8366b-115">Programming tips</span></span>

-   <span data-ttu-id="8366b-116">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="8366b-116">**Interop Considerations.**</span></span> <span data-ttu-id="8366b-117">Si interactúa con componentes no se han escrito para .NET Framework, por ejemplo objetos de automatización o COM, recuerde que `Long` tiene un ancho de datos diferente (32 bits) en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="8366b-117">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="8366b-118">Al pasar un argumento de 32 bits a esos componentes, declárelo como `Integer` en lugar de `Long` en el código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8366b-118">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="8366b-119">**De ampliación.**</span><span class="sxs-lookup"><span data-stu-id="8366b-119">**Widening.**</span></span> <span data-ttu-id="8366b-120">El `Long` tipo de datos se amplía a `Decimal`, `Single`, o `Double`.</span><span class="sxs-lookup"><span data-stu-id="8366b-120">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="8366b-121">Esto significa que puede convertir un tipo de datos `Long` en cualquiera de estos tipos sin que se produzca un error <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8366b-121">This means you can convert `Long` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="8366b-122">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="8366b-122">**Type Characters.**</span></span> <span data-ttu-id="8366b-123">Al agregar el carácter de tipo literal `L` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Long`.</span><span class="sxs-lookup"><span data-stu-id="8366b-123">Appending the literal type character `L` to a literal forces it to the `Long` data type.</span></span> <span data-ttu-id="8366b-124">Si se agrega el carácter de tipo identificador `&` a cualquier identificador, se convierte forzosamente al tipo `Long`.</span><span class="sxs-lookup"><span data-stu-id="8366b-124">Appending the identifier type character `&` to any identifier forces it to `Long`.</span></span>  
  
-   <span data-ttu-id="8366b-125">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="8366b-125">**Framework Type.**</span></span> <span data-ttu-id="8366b-126">El tipo correspondiente en .NET Framework es la estructura <xref:System.Int64?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8366b-126">The corresponding type in the .NET Framework is the <xref:System.Int64?displayProperty=nameWithType> structure.</span></span>  

## <a name="see-also"></a><span data-ttu-id="8366b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="8366b-127">See also</span></span>

<span data-ttu-id="8366b-128"><xref:System.Int64>[Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="8366b-128"><xref:System.Int64> [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="8366b-129">[Tipo de datos entero](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="8366b-129">[Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span></span>  
<span data-ttu-id="8366b-130">[Tipo de datos short](../../../visual-basic/language-reference/data-types/short-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="8366b-130">[Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md) </span></span>  
<span data-ttu-id="8366b-131">[Funciones de conversión de tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="8366b-131">[Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="8366b-132">[Resumen de la conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span><span class="sxs-lookup"><span data-stu-id="8366b-132">[Conversion Summary](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span></span>  
[<span data-ttu-id="8366b-133">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="8366b-133">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
