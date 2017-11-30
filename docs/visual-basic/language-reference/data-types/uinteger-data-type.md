---
title: UInteger (Tipo de datos)
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f3852bd56d11c19e327e6c2f3e23cfb082a54e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="uinteger-data-type"></a><span data-ttu-id="74afd-102">UInteger (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="74afd-102">UInteger data type</span></span>

<span data-ttu-id="74afd-103">Contiene enteros de 32 bits sin signo (4 bytes) comprendidos entre valor comprendido entre 0 y 4.294.967.295.</span><span class="sxs-lookup"><span data-stu-id="74afd-103">Holds unsigned 32-bit (4-byte) integers ranging in value from 0 through 4,294,967,295.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74afd-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74afd-104">Remarks</span></span>

 <span data-ttu-id="74afd-105">El `UInteger` tipo de datos proporciona el mayor valor sin signo en el ancho de datos más eficaz.</span><span class="sxs-lookup"><span data-stu-id="74afd-105">The `UInteger` data type provides the largest unsigned value in the most efficient data width.</span></span>  
  
 <span data-ttu-id="74afd-106">El valor predeterminado de `UInteger` es 0.</span><span class="sxs-lookup"><span data-stu-id="74afd-106">The default value of `UInteger` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="74afd-107">Asignaciones de literales</span><span class="sxs-lookup"><span data-stu-id="74afd-107">Literal assignments</span></span>

<span data-ttu-id="74afd-108">Puede declarar e inicializar un `UInteger` variable asignarle un decimal literal, un literal hexadecimal, un literal octal, o (a partir de Visual Basic de 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="74afd-108">You can declare and initialize a `UInteger` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="74afd-109">Si el literal entero está fuera del intervalo de `UInteger` (es decir, si es inferior a <xref:System.UInt32.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="74afd-109">If the integer literal is outside the range of `UInteger` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="74afd-110">En el ejemplo siguiente, los enteros que equivalen a 3 000 000 000 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `UInteger`.</span><span class="sxs-lookup"><span data-stu-id="74afd-110">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `UInteger` values.</span></span>
  
[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]  

> [!NOTE] 
> <span data-ttu-id="74afd-111">Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="74afd-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="74afd-112">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="74afd-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="74afd-113">A partir de Visual Basic de 2017, también puede utilizar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como en el ejemplo siguiente se muestra.</span><span class="sxs-lookup"><span data-stu-id="74afd-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]  

<span data-ttu-id="74afd-114">También pueden incluir literales numéricos el `UI` o `ui` [escriba carácter](../../programming-guide\language-features\data-types/type-characters.md) para denotar el `UInteger` tipo de datos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="74afd-114">Numeric literals can also include the `UI` or `ui` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `UInteger` data type, as the following example shows.</span></span>

```vb
Dim number = &H0FAC14D7ui
```

## <a name="programming-tips"></a><span data-ttu-id="74afd-115">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="74afd-115">Programming tips</span></span>

 <span data-ttu-id="74afd-116">El `UInteger` y `Integer` tipos de datos proporcionan un rendimiento óptimo en un procesador de 32 bits, porque los tipos enteros más pequeños (`UShort`, `Short`, `Byte`, y `SByte`), aunque éstos utilicen menos bits, tardan más tiempo en cargar, almacenar y recuperar.</span><span class="sxs-lookup"><span data-stu-id="74afd-116">The `UInteger` and `Integer` data types provide optimal performance on a 32-bit processor, because the smaller integer types (`UShort`, `Short`, `Byte`, and `SByte`), even though they use fewer bits, take more time to load, store, and fetch.</span></span>  
  
-   <span data-ttu-id="74afd-117">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="74afd-117">**Negative Numbers.**</span></span> <span data-ttu-id="74afd-118">Dado que `UInteger` es un tipo sin signo, no puede representar un número negativo.</span><span class="sxs-lookup"><span data-stu-id="74afd-118">Because `UInteger` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="74afd-119">Si se utiliza el operador unario menos (`-`) operador en una expresión que se evalúa como tipo `UInteger`, Visual Basic convierte la expresión `Long` primero.</span><span class="sxs-lookup"><span data-stu-id="74afd-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `UInteger`, Visual Basic converts the expression to `Long` first.</span></span>  
  
-   <span data-ttu-id="74afd-120">**Conformidad con CLS.**</span><span class="sxs-lookup"><span data-stu-id="74afd-120">**CLS Compliance.**</span></span> <span data-ttu-id="74afd-121">El `UInteger` tipo de datos no es parte de la [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código conforme a CLS no puede utilizar un componente que lo utiliza.</span><span class="sxs-lookup"><span data-stu-id="74afd-121">The `UInteger` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="74afd-122">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="74afd-122">**Interop Considerations.**</span></span> <span data-ttu-id="74afd-123">Si interactúa con componentes no se han escrito para .NET Framework, por ejemplo objetos de automatización o COM, tenga en cuenta que los tipos como `uint` puede tener un ancho de datos diferente (16 bits) en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="74afd-123">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `uint` can have a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="74afd-124">Al pasar un argumento de 16 bits a esos componentes, declárelo como `UShort` en lugar de `UInteger` en el código administrado de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="74afd-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
-   <span data-ttu-id="74afd-125">**De ampliación.**</span><span class="sxs-lookup"><span data-stu-id="74afd-125">**Widening.**</span></span> <span data-ttu-id="74afd-126">El `UInteger` tipo de datos se amplía a `Long`, `ULong`, `Decimal`, `Single`, y `Double`.</span><span class="sxs-lookup"><span data-stu-id="74afd-126">The `UInteger` data type widens to `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="74afd-127">Esto significa que se puede convertir `UInteger` a cualquiera de estos tipos sin que se produzca una <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="74afd-127">This means you can convert `UInteger` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="74afd-128">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="74afd-128">**Type Characters.**</span></span> <span data-ttu-id="74afd-129">Anexar los caracteres de tipo literal `UI` a un literal, se convierte a la `UInteger` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="74afd-129">Appending the literal type characters `UI` to a literal forces it to the `UInteger` data type.</span></span> <span data-ttu-id="74afd-130">`UInteger`no tiene ningún carácter de tipo identificador.</span><span class="sxs-lookup"><span data-stu-id="74afd-130">`UInteger` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="74afd-131">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="74afd-131">**Framework Type.**</span></span> <span data-ttu-id="74afd-132">El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="74afd-132">The corresponding type in the .NET Framework is the <xref:System.UInt32?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74afd-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="74afd-133">See Also</span></span>  
 <xref:System.UInt32>  
 [<span data-ttu-id="74afd-134">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="74afd-134">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="74afd-135">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="74afd-135">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="74afd-136">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="74afd-136">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="74afd-137">Llamar a una función de Windows que adopta tipos sin signo</span><span class="sxs-lookup"><span data-stu-id="74afd-137">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="74afd-138">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="74afd-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
