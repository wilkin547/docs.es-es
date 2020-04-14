---
title: Tipo de datos Decimal
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
ms.openlocfilehash: d4d868ba7c05cf3c2d538de1217231df91d4f43d
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243328"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="5c0db-102">Decimal (Tipo de datos, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c0db-102">Decimal Data Type (Visual Basic)</span></span>

<span data-ttu-id="5c0db-103">Contiene valores de 128 bits (16 bytes) firmados que representan números enteros de 96 bits (12 bytes) escalados por una potencia variable de 10.</span><span class="sxs-lookup"><span data-stu-id="5c0db-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="5c0db-104">El factor de escala especifica el número de dígitos a la derecha del punto decimal; oscila entre 0 y 28.</span><span class="sxs-lookup"><span data-stu-id="5c0db-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="5c0db-105">Con una escala de 0 (sin decimales), el mayor valor posible es +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span><span class="sxs-lookup"><span data-stu-id="5c0db-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="5c0db-106">Con 28 decimales, el valor más grande es +/-7.9228162514264337593543950335, y el valor distinto de cero más pequeño es +/-00000000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="5c0db-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>

## <a name="remarks"></a><span data-ttu-id="5c0db-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5c0db-107">Remarks</span></span>

<span data-ttu-id="5c0db-108">El `Decimal` tipo de datos proporciona el mayor número de dígitos significativos para un número.</span><span class="sxs-lookup"><span data-stu-id="5c0db-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="5c0db-109">Soporta hasta 29 dígitos significativos y puede representar valores superiores a 7.9228 x 10-28.</span><span class="sxs-lookup"><span data-stu-id="5c0db-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="5c0db-110">Es particularmente adecuado para cálculos, como financieros, que requieren un gran número de dígitos, pero no pueden tolerar errores de redondeo.</span><span class="sxs-lookup"><span data-stu-id="5c0db-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>

<span data-ttu-id="5c0db-111">El valor predeterminado de `Decimal` es 0.</span><span class="sxs-lookup"><span data-stu-id="5c0db-111">The default value of `Decimal` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="5c0db-112">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="5c0db-112">Programming Tips</span></span>

- <span data-ttu-id="5c0db-113">**Precisión.**</span><span class="sxs-lookup"><span data-stu-id="5c0db-113">**Precision.**</span></span> <span data-ttu-id="5c0db-114">`Decimal`no es un tipo de datos de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="5c0db-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="5c0db-115">La `Decimal` estructura contiene un valor entero binario, junto con un bit de signo y un factor de escala entero que especifica qué parte del valor es una fracción decimal.</span><span class="sxs-lookup"><span data-stu-id="5c0db-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="5c0db-116">Debido a `Decimal` esto, los números tienen una representación`Single` más `Double`precisa en la memoria que los tipos de punto flotante ( y ).</span><span class="sxs-lookup"><span data-stu-id="5c0db-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>

- <span data-ttu-id="5c0db-117">**Rendimiento.**</span><span class="sxs-lookup"><span data-stu-id="5c0db-117">**Performance.**</span></span> <span data-ttu-id="5c0db-118">El `Decimal` tipo de datos es el más lento de todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="5c0db-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="5c0db-119">Debe sopesar la importancia de la precisión frente al rendimiento antes de elegir un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="5c0db-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>

- <span data-ttu-id="5c0db-120">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="5c0db-120">**Widening.**</span></span> <span data-ttu-id="5c0db-121">El `Decimal` tipo de datos `Single` `Double`se amplía a o .</span><span class="sxs-lookup"><span data-stu-id="5c0db-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="5c0db-122">Esto significa que `Decimal` puede convertir a cualquiera <xref:System.OverflowException?displayProperty=nameWithType> de estos tipos sin encontrar un error.</span><span class="sxs-lookup"><span data-stu-id="5c0db-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="5c0db-123">**Trailing Zeros.**</span><span class="sxs-lookup"><span data-stu-id="5c0db-123">**Trailing Zeros.**</span></span> <span data-ttu-id="5c0db-124">Visual Basic no almacena ceros `Decimal` finales en un literal.</span><span class="sxs-lookup"><span data-stu-id="5c0db-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="5c0db-125">Sin `Decimal` embargo, una variable conserva los ceros finales adquiridos computacionalmente.</span><span class="sxs-lookup"><span data-stu-id="5c0db-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="5c0db-126">Esto se ilustra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5c0db-126">The following example illustrates this.</span></span>

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  <span data-ttu-id="5c0db-127">La salida `MsgBox` del ejemplo anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c0db-127">The output of `MsgBox` in the preceding example is as follows:</span></span>

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- <span data-ttu-id="5c0db-128">**Escriba Caracteres.**</span><span class="sxs-lookup"><span data-stu-id="5c0db-128">**Type Characters.**</span></span> <span data-ttu-id="5c0db-129">Al agregar el carácter de tipo literal `D` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="5c0db-129">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="5c0db-130">Si se agrega el carácter de tipo identificador `@` a cualquier identificador, se convierte forzosamente al tipo `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="5c0db-130">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>

- <span data-ttu-id="5c0db-131">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="5c0db-131">**Framework Type.**</span></span> <span data-ttu-id="5c0db-132">El tipo correspondiente en .NET Framework es la estructura <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c0db-132">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>

## <a name="range"></a><span data-ttu-id="5c0db-133">Intervalo</span><span class="sxs-lookup"><span data-stu-id="5c0db-133">Range</span></span>

 <span data-ttu-id="5c0db-134">Es posible que `D` deba utilizar el carácter `Decimal` de tipo para asignar un valor grande a una variable o constante.</span><span class="sxs-lookup"><span data-stu-id="5c0db-134">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="5c0db-135">Este requisito se debe a que `Long` el compilador interpreta un literal como a menos que un carácter de tipo literal siga el literal, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5c0db-135">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

<span data-ttu-id="5c0db-136">La declaración para `bigDec1` no produce un desbordamiento porque el valor que `Long`se le asigna se encuentra dentro del intervalo para .</span><span class="sxs-lookup"><span data-stu-id="5c0db-136">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="5c0db-137">El `Long` valor se puede `Decimal` asignar a la variable.</span><span class="sxs-lookup"><span data-stu-id="5c0db-137">The `Long` value can be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="5c0db-138">La declaración para `bigDec2` genera un error de desbordamiento porque el `Long`valor que se le asigna es demasiado grande para .</span><span class="sxs-lookup"><span data-stu-id="5c0db-138">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="5c0db-139">Dado que el literal numérico no se `Long`puede interpretar primero como `Decimal` un , no se puede asignar a la variable.</span><span class="sxs-lookup"><span data-stu-id="5c0db-139">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="5c0db-140">Para `bigDec3`, el `D` carácter de tipo literal resuelve el problema `Decimal` forzando `Long`al compilador a interpretar el literal como un archivo .</span><span class="sxs-lookup"><span data-stu-id="5c0db-140">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c0db-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5c0db-141">See also</span></span>

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5c0db-142">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="5c0db-142">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="5c0db-143">Tipo de datos Single</span><span class="sxs-lookup"><span data-stu-id="5c0db-143">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="5c0db-144">Tipo de datos Double</span><span class="sxs-lookup"><span data-stu-id="5c0db-144">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="5c0db-145">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="5c0db-145">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="5c0db-146">Resumen de las conversiones</span><span class="sxs-lookup"><span data-stu-id="5c0db-146">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="5c0db-147">Uso eficiente de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="5c0db-147">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
