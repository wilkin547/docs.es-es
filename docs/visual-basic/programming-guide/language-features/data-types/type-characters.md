---
title: Caracteres de tipo (Visual Basic)
ms.date: 01/31/2018
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals [Visual Basic]
- F literal type character [Visual Basic]
- '& identifier type character'
- type characters [Visual Basic]
- octal literals [Visual Basic]
- literals [Visual Basic], hexadecimal
- '&O prefix for octal values'
- literals [Visual Basic], default types
- defaults, literal types
- C literal type character [Visual Basic]
- type characters [Visual Basic], literal
- $ identifier type character
- L literal type character [Visual Basic]
- UI literal type characters [Visual Basic]
- default literal types [Visual Basic]
- D literal type character [Visual Basic]
- literals [Visual Basic], octal
- S literal type character [Visual Basic]
- '! identifier type character'
- US literal type characters [Visual Basic]
- '% identifier type character'
- data types [Visual Basic], type characters
- characters [Visual Basic], identifier type
- type characters [Visual Basic], identifier
- '# identifier type character'
- identifier type characters [Visual Basic]
- literal type characters [Visual Basic]
- I literal type character [Visual Basic]
- R literal type character [Visual Basic]
- '@ identifier type character'
- UL literal type characters [Visual Basic]
- literal types [Visual Basic], default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
ms.openlocfilehash: 1922282ece4dd90c8f55c8dea20ef2866d8b357c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181407"
---
# <a name="type-characters-visual-basic"></a><span data-ttu-id="0b9e0-102">Escriba caracteres (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b9e0-102">Type characters (Visual Basic)</span></span>

<span data-ttu-id="0b9e0-103">Además de especificar un tipo de datos en una instrucción de declaración, puede forzar el tipo de datos de algunos elementos de programación con un *carácter de tipo*.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-103">In addition to specifying a data type in a declaration statement, you can force the data type of some programming elements with a *type character*.</span></span> <span data-ttu-id="0b9e0-104">El carácter de tipo debe aparecer inmediatamente después del elemento, sin caracteres intermedios de ningún tipo.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-104">The type character must immediately follow the element, with no intervening characters of any kind.</span></span>

<span data-ttu-id="0b9e0-105">El carácter de tipo no es parte del nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-105">The type character is not part of the name of the element.</span></span> <span data-ttu-id="0b9e0-106">Puede hacer referencia a un elemento definido con un carácter de tipo sin el carácter de tipo.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-106">An element defined with a type character can be referenced without the type character.</span></span>

## <a name="identifier-type-characters"></a><span data-ttu-id="0b9e0-107">Caracteres de tipo identificador</span><span class="sxs-lookup"><span data-stu-id="0b9e0-107">Identifier type characters</span></span>

<span data-ttu-id="0b9e0-108">Visual Basic proporciona un conjunto de *caracteres de tipo identificador* que puede usar en una declaración para especificar el tipo de datos de una variable o constante.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-108">Visual Basic supplies a set of *identifier type characters* that you can use in a declaration to specify the data type of a variable or constant.</span></span> <span data-ttu-id="0b9e0-109">En la tabla siguiente se muestra los caracteres de tipo identificador disponibles con ejemplos de uso.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-109">The following table shows the available identifier type characters with examples of usage.</span></span>
  
|<span data-ttu-id="0b9e0-110">Carácter de tipo identificador</span><span class="sxs-lookup"><span data-stu-id="0b9e0-110">Identifier type character</span></span>|<span data-ttu-id="0b9e0-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="0b9e0-111">Data type</span></span>|<span data-ttu-id="0b9e0-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b9e0-112">Example</span></span>|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 <span data-ttu-id="0b9e0-113">No existe ningún carácter de tipo identificador para el `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, o `UShort` tipos de datos, o para ninguno tipos de datos compuestos como matrices o estructuras.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-113">No identifier type characters exist for the `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="0b9e0-114">En algunos casos, puede anexar el `$` de caracteres a una función de Visual Basic, por ejemplo `Left$` en lugar de `Left`, para obtener un valor devuelto de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-114">In some cases, you can append the `$` character to a Visual Basic function, for example `Left$` instead of `Left`, to obtain a returned value of type `String`.</span></span>

<span data-ttu-id="0b9e0-115">En todos los casos, el carácter de tipo identificador debe aparecer inmediatamente después del nombre del identificador.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-115">In all cases, the identifier type character must immediately follow the identifier name.</span></span>

## <a name="literal-type-characters"></a><span data-ttu-id="0b9e0-116">Caracteres de tipo literal</span><span class="sxs-lookup"><span data-stu-id="0b9e0-116">Literal type characters</span></span>

<span data-ttu-id="0b9e0-117">Un *literal* es una representación textual de un valor determinado de un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-117">A *literal* is a textual representation of a particular value of a data type.</span></span>  

### <a name="default-literal-types"></a><span data-ttu-id="0b9e0-118">Tipos literales predeterminados</span><span class="sxs-lookup"><span data-stu-id="0b9e0-118">Default literal types</span></span>

<span data-ttu-id="0b9e0-119">El formato de un literal tal como aparece en el código normalmente determina su tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-119">The form of a literal as it appears in your code ordinarily determines its data type.</span></span> <span data-ttu-id="0b9e0-120">En la tabla siguiente se muestra estos tipos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-120">The following table shows these default types.</span></span>  
  
|<span data-ttu-id="0b9e0-121">Formato textual de literal</span><span class="sxs-lookup"><span data-stu-id="0b9e0-121">Textual form of literal</span></span>|<span data-ttu-id="0b9e0-122">Tipo de datos predeterminado</span><span class="sxs-lookup"><span data-stu-id="0b9e0-122">Default data type</span></span>|<span data-ttu-id="0b9e0-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b9e0-123">Example</span></span>|  
|-----------------------------|-----------------------|-------------|  
|<span data-ttu-id="0b9e0-124">Numérico, ninguna parte fraccionaria</span><span class="sxs-lookup"><span data-stu-id="0b9e0-124">Numeric, no fractional part</span></span>|`Integer`|`2147483647`|  
|<span data-ttu-id="0b9e0-125">Numérico, ninguna parte fraccionaria, demasiado grande para `Integer`</span><span class="sxs-lookup"><span data-stu-id="0b9e0-125">Numeric, no fractional part, too large for `Integer`</span></span>|`Long`|`2147483648`|  
|<span data-ttu-id="0b9e0-126">Numérico, parte fraccionaria</span><span class="sxs-lookup"><span data-stu-id="0b9e0-126">Numeric, fractional part</span></span>|`Double`|`1.2`|  
|<span data-ttu-id="0b9e0-127">Entre comillas dobles</span><span class="sxs-lookup"><span data-stu-id="0b9e0-127">Enclosed in double quotation marks</span></span>|`String`|`"A"`|  
|<span data-ttu-id="0b9e0-128">Encerrado entre signos de número</span><span class="sxs-lookup"><span data-stu-id="0b9e0-128">Enclosed within number signs</span></span>|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a><span data-ttu-id="0b9e0-129">Tipos literales forzados</span><span class="sxs-lookup"><span data-stu-id="0b9e0-129">Forced literal types</span></span>

<span data-ttu-id="0b9e0-130">Visual Basic proporciona un conjunto de *caracteres de tipo literal*, lo que puede usar para forzar un literal se supone un tipo de datos que no sea el de su formulario indica.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-130">Visual Basic supplies a set of *literal type characters*, which you can use to force a literal to assume a data type other than the one its form indicates.</span></span> <span data-ttu-id="0b9e0-131">Para ello, anexe el carácter al final del literal.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-131">You do this by appending the character to the end of the literal.</span></span> <span data-ttu-id="0b9e0-132">La siguiente tabla muestra los caracteres de tipo literal disponibles con ejemplos de uso.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-132">The following table shows the available literal type characters with examples of usage.</span></span>
  
|<span data-ttu-id="0b9e0-133">Carácter de tipo literal</span><span class="sxs-lookup"><span data-stu-id="0b9e0-133">Literal type character</span></span>|<span data-ttu-id="0b9e0-134">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="0b9e0-134">Data type</span></span>|<span data-ttu-id="0b9e0-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b9e0-135">Example</span></span>|  
|----------------------------|---------------|-------------|  
|`S`|`Short`|`I = 347S`|
|`I`|`Integer`|`J = 347I`|
|`L`|`Long`|`K = 347L`|
|`D`|`Decimal`|`X = 347D`|
|`F`|`Single`|`Y = 347F`|
|`R`|`Double`|`Z = 347R`|
|`US`|`UShort`|`L = 347US`|
|`UI`|`UInteger`|`M = 347UI`|
|`UL`|`ULong`|`N = 347UL`|
|`C`|`Char`|`Q = "."C`|

<span data-ttu-id="0b9e0-136">No existe ningún carácter de tipo literal para el `Boolean`, `Byte`, `Date`, `Object`, `SByte`, o `String` tipos de datos, o para los tipos de datos compuestos como matrices o estructuras.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-136">No literal type characters exist for the `Boolean`, `Byte`, `Date`, `Object`, `SByte`, or `String` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="0b9e0-137">Los literales también pueden utilizar los caracteres de tipo identificador (`%`, `&`, `@`, `!`, `#`, `$`), igual que las variables, constantes y expresiones.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-137">Literals can also use the identifier type characters (`%`, `&`, `@`, `!`, `#`, `$`), as can variables, constants, and expressions.</span></span> <span data-ttu-id="0b9e0-138">Sin embargo, el literal de tipo caracteres (`S`, `I`, `L`, `D`, `F`, `R`, `C`) puede utilizarse solo con literales.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-138">However, the literal type characters (`S`, `I`, `L`, `D`, `F`, `R`, `C`) can be used only with literals.</span></span>

<span data-ttu-id="0b9e0-139">En todos los casos, el carácter de tipo literal debe seguir inmediatamente el valor literal.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-139">In all cases, the literal type character must immediately follow the literal value.</span></span>

## <a name="hexadecimal-binary-and-octal-literals"></a><span data-ttu-id="0b9e0-140">Literales hexadecimales, binarios y octales</span><span class="sxs-lookup"><span data-stu-id="0b9e0-140">Hexadecimal, binary, and octal literals</span></span>

<span data-ttu-id="0b9e0-141">Normalmente, el compilador interpreta un literal entero para estar en el sistema numérico decimal (base 10).</span><span class="sxs-lookup"><span data-stu-id="0b9e0-141">The compiler normally interprets an integer literal to be in the decimal (base 10) number system.</span></span> <span data-ttu-id="0b9e0-142">También puede definir un literal entero como un número hexadecimal (base 16) con el `&H` prefijo, como un número binario (base 2) con el `&B` prefijo y como un octal (base 8) con el `&O` prefijo.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-142">You can also define an integer literal as a hexadecimal (base 16) number with the `&H` prefix, as a binary (base 2) number with the `&B` prefix, and as an octal (base 8) number with the `&O` prefix.</span></span> <span data-ttu-id="0b9e0-143">Los dígitos que siguen el prefijo deben ser adecuados para el sistema numérico.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-143">The digits that follow the prefix must be appropriate for the number system.</span></span> <span data-ttu-id="0b9e0-144">En la tabla siguiente se ilustra esto.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-144">The following table illustrates this.</span></span>  
  
|<span data-ttu-id="0b9e0-145">Número base</span><span class="sxs-lookup"><span data-stu-id="0b9e0-145">Number base</span></span>|<span data-ttu-id="0b9e0-146">Prefijo</span><span class="sxs-lookup"><span data-stu-id="0b9e0-146">Prefix</span></span>|<span data-ttu-id="0b9e0-147">Valores de dígito válido</span><span class="sxs-lookup"><span data-stu-id="0b9e0-147">Valid digit values</span></span>|<span data-ttu-id="0b9e0-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b9e0-148">Example</span></span>|
|-----------------|------------|------------------------|-------------|
|<span data-ttu-id="0b9e0-149">Hexadecimal (base 16)</span><span class="sxs-lookup"><span data-stu-id="0b9e0-149">Hexadecimal (base 16)</span></span>|`&H`|<span data-ttu-id="0b9e0-150">0-9 y A-F</span><span class="sxs-lookup"><span data-stu-id="0b9e0-150">0-9 and A-F</span></span>|`&HFFFF`|
|<span data-ttu-id="0b9e0-151">Binario (base 2)</span><span class="sxs-lookup"><span data-stu-id="0b9e0-151">Binary (base 2)</span></span>|`&B`|<span data-ttu-id="0b9e0-152">0-1</span><span class="sxs-lookup"><span data-stu-id="0b9e0-152">0-1</span></span>|`&B01111100`|
|<span data-ttu-id="0b9e0-153">Octal (base 8)</span><span class="sxs-lookup"><span data-stu-id="0b9e0-153">Octal (base 8)</span></span>|`&O`|<span data-ttu-id="0b9e0-154">0-7</span><span class="sxs-lookup"><span data-stu-id="0b9e0-154">0-7</span></span>|`&O77`|

<span data-ttu-id="0b9e0-155">A partir de Visual Basic 2017, puede usar el carácter de subrayado (`_`) como un separador de grupo para mejorar la legibilidad de un literal entero.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-155">Starting in Visual Basic 2017, you can use the underscore character (`_`) as a group separator to enhance the readability of an integral literal.</span></span> <span data-ttu-id="0b9e0-156">En el ejemplo siguiente se usa el `_` caracteres para agrupar un literal binario en grupos de 8 bits:</span><span class="sxs-lookup"><span data-stu-id="0b9e0-156">The following example uses the `_` character to group a binary literal into 8-bit groups:</span></span>

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

<span data-ttu-id="0b9e0-157">Puede agregar un literal prefijado con un carácter de tipo literal.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-157">You can follow a prefixed literal with a literal type character.</span></span> <span data-ttu-id="0b9e0-158">En el ejemplo siguiente se muestra esto.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-158">The following example shows this.</span></span>

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

<span data-ttu-id="0b9e0-159">En el ejemplo anterior, `counter` tiene el valor decimal entre-32768, y `flags` tiene el valor decimal de + 32768.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-159">In the previous example, `counter` has the decimal value of -32768, and `flags` has the decimal value of +32768.</span></span>

<span data-ttu-id="0b9e0-160">A partir de Visual Basic 15.5, también puede usar el carácter de subrayado (`_`) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios u octales.</span><span class="sxs-lookup"><span data-stu-id="0b9e0-160">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="0b9e0-161">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0b9e0-161">For example:</span></span>

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a><span data-ttu-id="0b9e0-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b9e0-162">See Also</span></span>

 [<span data-ttu-id="0b9e0-163">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="0b9e0-163">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="0b9e0-164">Tipos de datos básicos</span><span class="sxs-lookup"><span data-stu-id="0b9e0-164">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="0b9e0-165">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="0b9e0-165">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="0b9e0-166">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0b9e0-166">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="0b9e0-167">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="0b9e0-167">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="0b9e0-168">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="0b9e0-168">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="0b9e0-169">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="0b9e0-169">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
