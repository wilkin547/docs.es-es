---
title: Short (Tipo de datos, Visual Basic)
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
author: rpetrusha
ms.author: ronpet
f1_keywords: vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: fef948debed69cf9fb7b0e6bb65eb0ddbe497a92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="short-data-type-visual-basic"></a><span data-ttu-id="00c5a-102">Tipo de datos short (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00c5a-102">Short data type (Visual Basic)</span></span>
<span data-ttu-id="00c5a-103">Contiene enteros con signo 16 bits (2 bytes) que intervalo entre -32.768 y 32.767.</span><span class="sxs-lookup"><span data-stu-id="00c5a-103">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00c5a-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="00c5a-104">Remarks</span></span>  
 <span data-ttu-id="00c5a-105">Use la `Short` tipo de datos para contener valores enteros que no requieren el ancho completo de datos de `Integer`.</span><span class="sxs-lookup"><span data-stu-id="00c5a-105">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span></span> <span data-ttu-id="00c5a-106">En algunos casos, common language runtime puede empaquetar su `Short` variables estrecha colaboración y ahorre consumo de memoria.</span><span class="sxs-lookup"><span data-stu-id="00c5a-106">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="00c5a-107">El valor predeterminado de `Short` es 0.</span><span class="sxs-lookup"><span data-stu-id="00c5a-107">The default value of `Short` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="00c5a-108">Asignaciones de literales</span><span class="sxs-lookup"><span data-stu-id="00c5a-108">Literal assignments</span></span>

<span data-ttu-id="00c5a-109">Puede declarar e inicializar un `Short` variable asignarle un decimal literal, un literal hexadecimal, un literal octal, o (a partir de Visual Basic de 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="00c5a-109">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="00c5a-110">Si el literal entero está fuera del intervalo de `Short` (es decir, si es inferior a <xref:System.Int16.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Int16.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="00c5a-110">If the integer literal is outside the range of `Short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="00c5a-111">En el siguiente ejemplo, enteros es igual a 1,034 que se representan como decimal, hexadecimal, y literales binarios se convierten implícitamente desde [entero](integer-data-type.md) a `Short` valores.</span><span class="sxs-lookup"><span data-stu-id="00c5a-111">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> <span data-ttu-id="00c5a-112">Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="00c5a-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="00c5a-113">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="00c5a-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="00c5a-114">A partir de Visual Basic de 2017, también puede utilizar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como en el ejemplo siguiente se muestra.</span><span class="sxs-lookup"><span data-stu-id="00c5a-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

<span data-ttu-id="00c5a-115">También pueden incluir literales numéricos el `S` [escriba carácter](../../programming-guide\language-features\data-types/type-characters.md) para denotar el `Short` tipo de datos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="00c5a-115">Numeric literals can also include the `S` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span></span>

```vb
Dim number = &H0326S
```

## <a name="programming-tips"></a><span data-ttu-id="00c5a-116">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="00c5a-116">Programming tips</span></span>

-   <span data-ttu-id="00c5a-117">**De ampliación.**</span><span class="sxs-lookup"><span data-stu-id="00c5a-117">**Widening.**</span></span> <span data-ttu-id="00c5a-118">El `Short` tipo de datos se amplía a `Integer`, `Long`, `Decimal`, `Single`, o `Double`.</span><span class="sxs-lookup"><span data-stu-id="00c5a-118">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="00c5a-119">Esto significa que puede convertir un tipo de datos `Short` en cualquiera de estos tipos sin que se produzca un error <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="00c5a-119">This means you can convert `Short` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="00c5a-120">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="00c5a-120">**Type Characters.**</span></span> <span data-ttu-id="00c5a-121">Al agregar el carácter de tipo literal `S` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Short`.</span><span class="sxs-lookup"><span data-stu-id="00c5a-121">Appending the literal type character `S` to a literal forces it to the `Short` data type.</span></span> <span data-ttu-id="00c5a-122">`Short`no tiene ningún carácter de tipo identificador.</span><span class="sxs-lookup"><span data-stu-id="00c5a-122">`Short` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="00c5a-123">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="00c5a-123">**Framework Type.**</span></span> <span data-ttu-id="00c5a-124">El tipo correspondiente en .NET Framework es la estructura <xref:System.Int16?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="00c5a-124">The corresponding type in the .NET Framework is the <xref:System.Int16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00c5a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="00c5a-125">See also</span></span>

 <xref:System.Int16?displayProperty=nameWithType>  
 [<span data-ttu-id="00c5a-126">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="00c5a-126">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="00c5a-127">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="00c5a-127">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="00c5a-128">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="00c5a-128">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="00c5a-129">Integer (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="00c5a-129">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="00c5a-130">Long (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="00c5a-130">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [<span data-ttu-id="00c5a-131">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="00c5a-131">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
