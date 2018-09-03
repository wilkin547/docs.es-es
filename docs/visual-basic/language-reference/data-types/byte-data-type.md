---
title: Byte (Tipo de datos, Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b106005ff07f55e05ae66dba94041cd8b5c24bb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482303"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="d1e1a-102">Tipo de datos de byte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1e1a-102">Byte data type (Visual Basic)</span></span>
<span data-ttu-id="d1e1a-103">Contiene enteros de (1 bytes) de 8 bits sin signo que van de un valor comprendido entre 0 y 255.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="d1e1a-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d1e1a-104">Remarks</span></span>

<span data-ttu-id="d1e1a-105">Use el `Byte` tipo de datos para contener datos binarios.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="d1e1a-106">El valor predeterminado de `Byte` es 0.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="d1e1a-107">Asignaciones de literales</span><span class="sxs-lookup"><span data-stu-id="d1e1a-107">Literal assignments</span></span>

<span data-ttu-id="d1e1a-108">Puede declarar e inicializar un `Byte` variable mediante la asignación de un literal decimal, un literal hexadecimal, un literal octal, o (a partir de 2017 Visual Basic) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="d1e1a-109">Si el literal entero está fuera del intervalo de un `Byte` (es decir, si es menor que <xref:System.Byte.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Byte.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="d1e1a-110">En el ejemplo siguiente, los enteros que equivalen a 201 que se representan como decimal, hexadecimal, y literales binarios se convierten implícitamente de [entero](integer-data-type.md) a `byte` valores.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="d1e1a-111">Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="d1e1a-112">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="d1e1a-113">A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como en el ejemplo siguiente se muestra.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="d1e1a-114">A partir de Visual Basic 15.5, también puede usar el carácter de subrayado (`_`) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios u octales.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="d1e1a-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d1e1a-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="d1e1a-116">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="d1e1a-116">Programming tips</span></span>

-   <span data-ttu-id="d1e1a-117">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="d1e1a-117">**Negative Numbers.**</span></span> <span data-ttu-id="d1e1a-118">Dado que `Byte` es un tipo sin signo, que no puede representar un número negativo.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="d1e1a-119">Si usa el operador unario menos (`-`) operador en una expresión que se evalúa como tipo `Byte`, Visual Basic convierte la expresión a `Short` primero.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
-   <span data-ttu-id="d1e1a-120">**Conversiones de formato.**</span><span class="sxs-lookup"><span data-stu-id="d1e1a-120">**Format Conversions.**</span></span> <span data-ttu-id="d1e1a-121">Cuando Visual Basic lee o escribe archivos, o cuando llama a archivos DLL, métodos y propiedades, puede convertir automáticamente entre los formatos de datos.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="d1e1a-122">Datos binarios almacenados en `Byte` variables y matrices se conservan durante estas conversiones de formato.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="d1e1a-123">No se debe usar un `String` variable para los datos binarios, ya que su contenido puede dañarse durante la conversión entre los formatos ANSI y Unicode.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

-   <span data-ttu-id="d1e1a-124">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="d1e1a-124">**Widening.**</span></span> <span data-ttu-id="d1e1a-125">El `Byte` tipo de datos se amplía a `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, o `Double`.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="d1e1a-126">Esto significa que se puede convertir `Byte` a cualquiera de estos tipos sin que se produzca una <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="d1e1a-127">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="d1e1a-127">**Type Characters.**</span></span> <span data-ttu-id="d1e1a-128">`Byte` no tiene ningún carácter de tipo literal o un carácter de tipo identificador.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-128">`Byte` has no literal type character or identifier type character.</span></span>

-   <span data-ttu-id="d1e1a-129">**Tipo de marco de trabajo.**</span><span class="sxs-lookup"><span data-stu-id="d1e1a-129">**Framework Type.**</span></span> <span data-ttu-id="d1e1a-130">El tipo correspondiente en .NET Framework es la estructura <xref:System.Byte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="d1e1a-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1e1a-131">Example</span></span>

 <span data-ttu-id="d1e1a-132">En el ejemplo siguiente, `b` es un `Byte` variable.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="d1e1a-133">Las instrucciones muestran el intervalo de la variable y la aplicación de operadores de desplazamiento de bits.</span><span class="sxs-lookup"><span data-stu-id="d1e1a-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

[!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  

## <a name="see-also"></a><span data-ttu-id="d1e1a-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1e1a-134">See Also</span></span>

 <xref:System.Byte?displayProperty=nameWithType>  
 [<span data-ttu-id="d1e1a-135">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="d1e1a-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="d1e1a-136">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="d1e1a-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="d1e1a-137">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="d1e1a-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="d1e1a-138">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="d1e1a-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
