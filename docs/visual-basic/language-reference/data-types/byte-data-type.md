---
title: Byte (Tipo de datos, Visual Basic)
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6475ff3ed905abb022a9ef60204c04b45130ae22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="b924e-102">Tipo de datos de byte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b924e-102">Byte data type (Visual Basic)</span></span>
<span data-ttu-id="b924e-103">Contiene enteros de (1-bytes) de 8 bits sin signo que van de un valor comprendido entre 0 y 255.</span><span class="sxs-lookup"><span data-stu-id="b924e-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="b924e-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b924e-104">Remarks</span></span>

<span data-ttu-id="b924e-105">Use la `Byte` tipo de datos para contener datos binarios.</span><span class="sxs-lookup"><span data-stu-id="b924e-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="b924e-106">El valor predeterminado de `Byte` es 0.</span><span class="sxs-lookup"><span data-stu-id="b924e-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="b924e-107">Asignaciones de literales</span><span class="sxs-lookup"><span data-stu-id="b924e-107">Literal assignments</span></span>

<span data-ttu-id="b924e-108">Puede declarar e inicializar un `Byte` variable asignarle un decimal literal, un literal hexadecimal, un literal octal, o (a partir de Visual Basic de 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="b924e-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="b924e-109">Si el literal entero está fuera del intervalo de un `Byte` (es decir, si es inferior a <xref:System.Byte.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Byte.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="b924e-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="b924e-110">En el siguiente ejemplo, enteros es igual a 201 que se representan como decimal, hexadecimal, y literales binarios se convierten implícitamente desde [entero](integer-data-type.md) a `byte` valores.</span><span class="sxs-lookup"><span data-stu-id="b924e-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="b924e-111">Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="b924e-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="b924e-112">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="b924e-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="b924e-113">A partir de Visual Basic de 2017, también puede utilizar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como en el ejemplo siguiente se muestra.</span><span class="sxs-lookup"><span data-stu-id="b924e-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

## <a name="programming-tips"></a><span data-ttu-id="b924e-114">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="b924e-114">Programming tips</span></span>

-   <span data-ttu-id="b924e-115">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="b924e-115">**Negative Numbers.**</span></span> <span data-ttu-id="b924e-116">Dado que `Byte` es un tipo sin signo, no puede representar un número negativo.</span><span class="sxs-lookup"><span data-stu-id="b924e-116">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="b924e-117">Si se utiliza el operador unario menos (`-`) operador en una expresión que se evalúa como tipo `Byte`, Visual Basic convierte la expresión `Short` primero.</span><span class="sxs-lookup"><span data-stu-id="b924e-117">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
-   <span data-ttu-id="b924e-118">**Conversiones de formato.**</span><span class="sxs-lookup"><span data-stu-id="b924e-118">**Format Conversions.**</span></span> <span data-ttu-id="b924e-119">Cuando Visual Basic lee o escribe archivos o cuando llama a archivos DLL, métodos y propiedades, puede convertir automáticamente entre los formatos de datos.</span><span class="sxs-lookup"><span data-stu-id="b924e-119">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="b924e-120">Datos binarios almacenados en `Byte` matrices y variables se conservan durante estas conversiones de formato.</span><span class="sxs-lookup"><span data-stu-id="b924e-120">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="b924e-121">No se debe usar un `String` variable para los datos binarios, ya que su contenido puede dañarse durante la conversión entre los formatos ANSI y Unicode.</span><span class="sxs-lookup"><span data-stu-id="b924e-121">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

-   <span data-ttu-id="b924e-122">**De ampliación.**</span><span class="sxs-lookup"><span data-stu-id="b924e-122">**Widening.**</span></span> <span data-ttu-id="b924e-123">El `Byte` tipo de datos se amplía a `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, o `Double`.</span><span class="sxs-lookup"><span data-stu-id="b924e-123">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="b924e-124">Esto significa que se puede convertir `Byte` a cualquiera de estos tipos sin que se produzca una <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="b924e-124">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="b924e-125">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="b924e-125">**Type Characters.**</span></span> <span data-ttu-id="b924e-126">`Byte`no tiene ningún carácter de tipo literal ni caracteres de tipo identificador.</span><span class="sxs-lookup"><span data-stu-id="b924e-126">`Byte` has no literal type character or identifier type character.</span></span>

-   <span data-ttu-id="b924e-127">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="b924e-127">**Framework Type.**</span></span> <span data-ttu-id="b924e-128">El tipo correspondiente en .NET Framework es la estructura <xref:System.Byte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b924e-128">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="b924e-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b924e-129">Example</span></span>

 <span data-ttu-id="b924e-130">En el ejemplo siguiente, `b` es un `Byte` variable.</span><span class="sxs-lookup"><span data-stu-id="b924e-130">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="b924e-131">Las instrucciones muestran el intervalo de la variable y la aplicación de operadores de desplazamiento de bits a ella.</span><span class="sxs-lookup"><span data-stu-id="b924e-131">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

[!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  

## <a name="see-also"></a><span data-ttu-id="b924e-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="b924e-132">See Also</span></span>

 <xref:System.Byte?displayProperty=nameWithType>  
 [<span data-ttu-id="b924e-133">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="b924e-133">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="b924e-134">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="b924e-134">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="b924e-135">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="b924e-135">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="b924e-136">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="b924e-136">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
