---
title: Decimal (Tipo de datos, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: bab5a0bd7e0a85d550362bc3c1166566f6dcb81b
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512771"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="43db4-102">Decimal (Tipo de datos, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43db4-102">Decimal Data Type (Visual Basic)</span></span>

<span data-ttu-id="43db4-103">Contiene valores con signo de 128 bits (16 bytes) que representan números enteros de 96 bits (12 bytes) escalados por una potencia variable de 10.</span><span class="sxs-lookup"><span data-stu-id="43db4-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="43db4-104">El factor de escala especifica el número de dígitos a la derecha del separador decimal; está comprendido entre 0 y 28.</span><span class="sxs-lookup"><span data-stu-id="43db4-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="43db4-105">Con una escala de 0 (sin posiciones decimales), el mayor valor posible es +/-79.228.162.514.264.337.593.543.950.335 (+/-7.9228162514264337593543950335E + 28).</span><span class="sxs-lookup"><span data-stu-id="43db4-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="43db4-106">Con 28 posiciones decimales, el valor más grande es +/-7,9228162514264337593543950335 y el menor valor distinto de cero es +/-0,0000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="43db4-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>

## <a name="remarks"></a><span data-ttu-id="43db4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43db4-107">Remarks</span></span>

<span data-ttu-id="43db4-108">El `Decimal` tipo de datos proporciona el mayor número de dígitos significativos para un número.</span><span class="sxs-lookup"><span data-stu-id="43db4-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="43db4-109">Admite hasta 29 dígitos significativos y puede representar valores que superan los 7,9228 x 10 ^ 28.</span><span class="sxs-lookup"><span data-stu-id="43db4-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="43db4-110">Es especialmente adecuado para los cálculos, como finanzas, que requieren un gran número de dígitos, pero no pueden tolerar errores de redondeo.</span><span class="sxs-lookup"><span data-stu-id="43db4-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>

<span data-ttu-id="43db4-111">El valor predeterminado de `Decimal` es 0.</span><span class="sxs-lookup"><span data-stu-id="43db4-111">The default value of `Decimal` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="43db4-112">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="43db4-112">Programming Tips</span></span>

- <span data-ttu-id="43db4-113">**Precisión.**</span><span class="sxs-lookup"><span data-stu-id="43db4-113">**Precision.**</span></span> <span data-ttu-id="43db4-114">`Decimal`no es un tipo de datos de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="43db4-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="43db4-115">La `Decimal` estructura contiene un valor entero binario, junto con un bit de signo y un factor de escala entero que especifica qué parte del valor es una fracción decimal.</span><span class="sxs-lookup"><span data-stu-id="43db4-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="43db4-116">Debido a esto, `Decimal` los números tienen una representación más precisa en la memoria que los tipos de`Single` punto `Double`flotante (y).</span><span class="sxs-lookup"><span data-stu-id="43db4-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>

- <span data-ttu-id="43db4-117">**Rendimiento.**</span><span class="sxs-lookup"><span data-stu-id="43db4-117">**Performance.**</span></span> <span data-ttu-id="43db4-118">El `Decimal` tipo de datos es el más lento de todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="43db4-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="43db4-119">Debe sopesar la importancia de la precisión respecto al rendimiento antes de elegir un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="43db4-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>

- <span data-ttu-id="43db4-120">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="43db4-120">**Widening.**</span></span> <span data-ttu-id="43db4-121">El `Decimal` tipo de datos se amplía `Single` a `Double`o.</span><span class="sxs-lookup"><span data-stu-id="43db4-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="43db4-122">Esto significa que puede convertir `Decimal` en cualquiera de estos tipos sin que se produzca un <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="43db4-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="43db4-123">**Ceros a la derecha.**</span><span class="sxs-lookup"><span data-stu-id="43db4-123">**Trailing Zeros.**</span></span> <span data-ttu-id="43db4-124">Visual Basic no almacena los ceros finales en un `Decimal` literal.</span><span class="sxs-lookup"><span data-stu-id="43db4-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="43db4-125">Sin embargo, `Decimal` una variable conserva los ceros finales adquiridos de cálculo.</span><span class="sxs-lookup"><span data-stu-id="43db4-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="43db4-126">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="43db4-126">The following example illustrates this.</span></span>

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  <span data-ttu-id="43db4-127">La salida de `MsgBox` en el ejemplo anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="43db4-127">The output of `MsgBox` in the preceding example is as follows:</span></span>

  ```
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- <span data-ttu-id="43db4-128">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="43db4-128">**Type Characters.**</span></span> <span data-ttu-id="43db4-129">Al agregar el carácter de tipo literal `D` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43db4-129">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="43db4-130">Si se agrega el carácter de tipo identificador `@` a cualquier identificador, se convierte forzosamente al tipo `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43db4-130">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>

- <span data-ttu-id="43db4-131">**Tipo de marco.**</span><span class="sxs-lookup"><span data-stu-id="43db4-131">**Framework Type.**</span></span> <span data-ttu-id="43db4-132">El tipo correspondiente en .NET Framework es la estructura <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="43db4-132">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>

## <a name="range"></a><span data-ttu-id="43db4-133">Intervalo</span><span class="sxs-lookup"><span data-stu-id="43db4-133">Range</span></span>
 <span data-ttu-id="43db4-134">Es posible que tenga que usar `D` el carácter de tipo para asignar un valor grande `Decimal` a una variable o constante.</span><span class="sxs-lookup"><span data-stu-id="43db4-134">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="43db4-135">Este requisito se debe a que el compilador interpreta `Long` un literal como a menos que un carácter de tipo literal siga el literal, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="43db4-135">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

<span data-ttu-id="43db4-136">La declaración de `bigDec1` no produce un desbordamiento porque el valor que se le asigna se encuentra dentro del intervalo de `Long`.</span><span class="sxs-lookup"><span data-stu-id="43db4-136">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="43db4-137">El `Long` valor se puede asignar a la `Decimal` variable.</span><span class="sxs-lookup"><span data-stu-id="43db4-137">The `Long` value can be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="43db4-138">La declaración de `bigDec2` genera un error de desbordamiento porque el valor asignado a él es demasiado grande para. `Long`</span><span class="sxs-lookup"><span data-stu-id="43db4-138">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="43db4-139">Dado que el literal numérico no se puede interpretar primero `Long`como, no se puede asignar a `Decimal` la variable.</span><span class="sxs-lookup"><span data-stu-id="43db4-139">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="43db4-140">En `bigDec3`el caso de, el `D` carácter de tipo literal soluciona el problema obligando al compilador a `Decimal` interpretar el literal como en `Long`lugar de como.</span><span class="sxs-lookup"><span data-stu-id="43db4-140">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>

## <a name="see-also"></a><span data-ttu-id="43db4-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="43db4-141">See also</span></span>

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [<span data-ttu-id="43db4-142">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="43db4-142">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="43db4-143">Single (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="43db4-143">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="43db4-144">Double (tipos de datos)</span><span class="sxs-lookup"><span data-stu-id="43db4-144">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="43db4-145">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="43db4-145">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="43db4-146">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="43db4-146">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="43db4-147">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="43db4-147">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
