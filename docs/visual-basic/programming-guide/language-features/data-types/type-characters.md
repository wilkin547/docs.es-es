---
title: Caracteres de tipo
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
ms.openlocfilehash: a48260694c1dfcbbb8f804f220fe89b1663c7319
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393083"
---
# <a name="type-characters-visual-basic"></a><span data-ttu-id="09fcc-102">Caracteres de tipo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09fcc-102">Type characters (Visual Basic)</span></span>

<span data-ttu-id="09fcc-103">Además de especificar un tipo de datos en una instrucción de declaración, puede forzar el tipo de datos de algunos elementos de programación con un *carácter de tipo*.</span><span class="sxs-lookup"><span data-stu-id="09fcc-103">In addition to specifying a data type in a declaration statement, you can force the data type of some programming elements with a *type character*.</span></span> <span data-ttu-id="09fcc-104">El carácter de tipo debe ir inmediatamente después del elemento, sin caracteres intermedios de ningún tipo.</span><span class="sxs-lookup"><span data-stu-id="09fcc-104">The type character must immediately follow the element, with no intervening characters of any kind.</span></span>

<span data-ttu-id="09fcc-105">El carácter de tipo no forma parte del nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="09fcc-105">The type character is not part of the name of the element.</span></span> <span data-ttu-id="09fcc-106">Se puede hacer referencia a un elemento definido con un carácter de tipo sin el carácter de tipo.</span><span class="sxs-lookup"><span data-stu-id="09fcc-106">An element defined with a type character can be referenced without the type character.</span></span>

## <a name="identifier-type-characters"></a><span data-ttu-id="09fcc-107">Caracteres de tipo de identificador</span><span class="sxs-lookup"><span data-stu-id="09fcc-107">Identifier type characters</span></span>

<span data-ttu-id="09fcc-108">Visual Basic proporciona un conjunto de *caracteres de tipo de identificador* que puede usar en una declaración para especificar el tipo de datos de una variable o constante.</span><span class="sxs-lookup"><span data-stu-id="09fcc-108">Visual Basic supplies a set of *identifier type characters* that you can use in a declaration to specify the data type of a variable or constant.</span></span> <span data-ttu-id="09fcc-109">En la tabla siguiente se muestran los caracteres de tipo de identificador disponibles con ejemplos de uso.</span><span class="sxs-lookup"><span data-stu-id="09fcc-109">The following table shows the available identifier type characters with examples of usage.</span></span>
  
|<span data-ttu-id="09fcc-110">Carácter de tipo de identificador</span><span class="sxs-lookup"><span data-stu-id="09fcc-110">Identifier type character</span></span>|<span data-ttu-id="09fcc-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="09fcc-111">Data type</span></span>|<span data-ttu-id="09fcc-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09fcc-112">Example</span></span>|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 <span data-ttu-id="09fcc-113">No existen caracteres de tipo identificador para los `Boolean` tipos de datos,,,,,,,, `Byte` `Char` `Date` `Object` `SByte` `Short` `UInteger` `ULong` o `UShort` , ni para los tipos de datos compuestos como matrices o estructuras.</span><span class="sxs-lookup"><span data-stu-id="09fcc-113">No identifier type characters exist for the `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="09fcc-114">En algunos casos, puede anexar el `$` carácter a una Visual Basic función, por ejemplo, en `Left$` lugar de `Left` , para obtener un valor devuelto de tipo `String` .</span><span class="sxs-lookup"><span data-stu-id="09fcc-114">In some cases, you can append the `$` character to a Visual Basic function, for example `Left$` instead of `Left`, to obtain a returned value of type `String`.</span></span>

<span data-ttu-id="09fcc-115">En todos los casos, el carácter de tipo de identificador debe aparecer inmediatamente después del nombre del identificador.</span><span class="sxs-lookup"><span data-stu-id="09fcc-115">In all cases, the identifier type character must immediately follow the identifier name.</span></span>

## <a name="literal-type-characters"></a><span data-ttu-id="09fcc-116">Caracteres de tipo literal</span><span class="sxs-lookup"><span data-stu-id="09fcc-116">Literal type characters</span></span>

<span data-ttu-id="09fcc-117">Un *literal* es una representación textual de un valor determinado de un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="09fcc-117">A *literal* is a textual representation of a particular value of a data type.</span></span>  

### <a name="default-literal-types"></a><span data-ttu-id="09fcc-118">Tipos literales predeterminados</span><span class="sxs-lookup"><span data-stu-id="09fcc-118">Default literal types</span></span>

<span data-ttu-id="09fcc-119">La forma de un literal tal como aparece en el código suele determinar su tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="09fcc-119">The form of a literal as it appears in your code ordinarily determines its data type.</span></span> <span data-ttu-id="09fcc-120">En la tabla siguiente se muestran estos tipos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="09fcc-120">The following table shows these default types.</span></span>  
  
|<span data-ttu-id="09fcc-121">Forma textual de literal</span><span class="sxs-lookup"><span data-stu-id="09fcc-121">Textual form of literal</span></span>|<span data-ttu-id="09fcc-122">Tipo de datos predeterminado</span><span class="sxs-lookup"><span data-stu-id="09fcc-122">Default data type</span></span>|<span data-ttu-id="09fcc-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09fcc-123">Example</span></span>|  
|-----------------------------|-----------------------|-------------|  
|<span data-ttu-id="09fcc-124">Numeric, sin parte fraccionaria</span><span class="sxs-lookup"><span data-stu-id="09fcc-124">Numeric, no fractional part</span></span>|`Integer`|`2147483647`|  
|<span data-ttu-id="09fcc-125">Numérico, sin parte fraccionaria, demasiado grande para`Integer`</span><span class="sxs-lookup"><span data-stu-id="09fcc-125">Numeric, no fractional part, too large for `Integer`</span></span>|`Long`|`2147483648`|  
|<span data-ttu-id="09fcc-126">Numeric, parte fraccionaria</span><span class="sxs-lookup"><span data-stu-id="09fcc-126">Numeric, fractional part</span></span>|`Double`|`1.2`|  
|<span data-ttu-id="09fcc-127">Entre comillas dobles</span><span class="sxs-lookup"><span data-stu-id="09fcc-127">Enclosed in double quotation marks</span></span>|`String`|`"A"`|  
|<span data-ttu-id="09fcc-128">Entre signos de número</span><span class="sxs-lookup"><span data-stu-id="09fcc-128">Enclosed within number signs</span></span>|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a><span data-ttu-id="09fcc-129">Tipos de literales forzados</span><span class="sxs-lookup"><span data-stu-id="09fcc-129">Forced literal types</span></span>

<span data-ttu-id="09fcc-130">Visual Basic proporciona un conjunto de *caracteres de tipo literal*, que puede usar para forzar que un literal asuma un tipo de datos distinto del que indica su forma.</span><span class="sxs-lookup"><span data-stu-id="09fcc-130">Visual Basic supplies a set of *literal type characters*, which you can use to force a literal to assume a data type other than the one its form indicates.</span></span> <span data-ttu-id="09fcc-131">Para ello, Anexe el carácter al final del literal.</span><span class="sxs-lookup"><span data-stu-id="09fcc-131">You do this by appending the character to the end of the literal.</span></span> <span data-ttu-id="09fcc-132">En la tabla siguiente se muestran los caracteres de tipo literal disponibles con ejemplos de uso.</span><span class="sxs-lookup"><span data-stu-id="09fcc-132">The following table shows the available literal type characters with examples of usage.</span></span>
  
|<span data-ttu-id="09fcc-133">Carácter de tipo literal</span><span class="sxs-lookup"><span data-stu-id="09fcc-133">Literal type character</span></span>|<span data-ttu-id="09fcc-134">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="09fcc-134">Data type</span></span>|<span data-ttu-id="09fcc-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09fcc-135">Example</span></span>|  
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

<span data-ttu-id="09fcc-136">No existen caracteres de tipo literal para `Boolean` los `Byte` tipos de datos,, `Date` ,, `Object` `SByte` o `String` , ni para los tipos de datos compuestos como matrices o estructuras.</span><span class="sxs-lookup"><span data-stu-id="09fcc-136">No literal type characters exist for the `Boolean`, `Byte`, `Date`, `Object`, `SByte`, or `String` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="09fcc-137">Los literales también pueden usar los caracteres de tipo de identificador ( `%` , `&` , `@` , `!` , `#` , `$` ), como pueden ser variables, constantes y expresiones.</span><span class="sxs-lookup"><span data-stu-id="09fcc-137">Literals can also use the identifier type characters (`%`, `&`, `@`, `!`, `#`, `$`), as can variables, constants, and expressions.</span></span> <span data-ttu-id="09fcc-138">Sin embargo, los caracteres de tipo literal ( `S` , `I` , `L` , `D` , `F` , `R` , `C` ) solo se pueden usar con literales.</span><span class="sxs-lookup"><span data-stu-id="09fcc-138">However, the literal type characters (`S`, `I`, `L`, `D`, `F`, `R`, `C`) can be used only with literals.</span></span>

<span data-ttu-id="09fcc-139">En todos los casos, el carácter de tipo literal debe seguir inmediatamente al valor literal.</span><span class="sxs-lookup"><span data-stu-id="09fcc-139">In all cases, the literal type character must immediately follow the literal value.</span></span>

## <a name="hexadecimal-binary-and-octal-literals"></a><span data-ttu-id="09fcc-140">Literales hexadecimales, binarios y octales</span><span class="sxs-lookup"><span data-stu-id="09fcc-140">Hexadecimal, binary, and octal literals</span></span>

<span data-ttu-id="09fcc-141">Normalmente, el compilador interpreta un literal entero para que esté en el sistema numérico decimal (base 10).</span><span class="sxs-lookup"><span data-stu-id="09fcc-141">The compiler normally interprets an integer literal to be in the decimal (base 10) number system.</span></span> <span data-ttu-id="09fcc-142">También puede definir un literal entero como un número hexadecimal (base 16) con el `&H` prefijo, como un número binario (base 2) con el `&B` prefijo, y como un número octal (base 8) con el `&O` prefijo.</span><span class="sxs-lookup"><span data-stu-id="09fcc-142">You can also define an integer literal as a hexadecimal (base 16) number with the `&H` prefix, as a binary (base 2) number with the `&B` prefix, and as an octal (base 8) number with the `&O` prefix.</span></span> <span data-ttu-id="09fcc-143">Los dígitos que siguen al prefijo deben ser adecuados para el sistema numérico.</span><span class="sxs-lookup"><span data-stu-id="09fcc-143">The digits that follow the prefix must be appropriate for the number system.</span></span> <span data-ttu-id="09fcc-144">En la tabla siguiente se muestra esto.</span><span class="sxs-lookup"><span data-stu-id="09fcc-144">The following table illustrates this.</span></span>  
  
|<span data-ttu-id="09fcc-145">Base numérica</span><span class="sxs-lookup"><span data-stu-id="09fcc-145">Number base</span></span>|<span data-ttu-id="09fcc-146">Prefijo</span><span class="sxs-lookup"><span data-stu-id="09fcc-146">Prefix</span></span>|<span data-ttu-id="09fcc-147">Valores de dígitos válidos</span><span class="sxs-lookup"><span data-stu-id="09fcc-147">Valid digit values</span></span>|<span data-ttu-id="09fcc-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09fcc-148">Example</span></span>|
|-----------------|------------|------------------------|-------------|
|<span data-ttu-id="09fcc-149">Hexadecimal (base 16)</span><span class="sxs-lookup"><span data-stu-id="09fcc-149">Hexadecimal (base 16)</span></span>|`&H`|<span data-ttu-id="09fcc-150">0-9 y A-F</span><span class="sxs-lookup"><span data-stu-id="09fcc-150">0-9 and A-F</span></span>|`&HFFFF`|
|<span data-ttu-id="09fcc-151">Binario (base 2)</span><span class="sxs-lookup"><span data-stu-id="09fcc-151">Binary (base 2)</span></span>|`&B`|<span data-ttu-id="09fcc-152">0-1</span><span class="sxs-lookup"><span data-stu-id="09fcc-152">0-1</span></span>|`&B01111100`|
|<span data-ttu-id="09fcc-153">Octal (base 8)</span><span class="sxs-lookup"><span data-stu-id="09fcc-153">Octal (base 8)</span></span>|`&O`|<span data-ttu-id="09fcc-154">0-7</span><span class="sxs-lookup"><span data-stu-id="09fcc-154">0-7</span></span>|`&O77`|

<span data-ttu-id="09fcc-155">A partir de Visual Basic 2017, puede usar el carácter de subrayado ( `_` ) como separador de grupos para mejorar la legibilidad de un literal entero.</span><span class="sxs-lookup"><span data-stu-id="09fcc-155">Starting in Visual Basic 2017, you can use the underscore character (`_`) as a group separator to enhance the readability of an integral literal.</span></span> <span data-ttu-id="09fcc-156">En el ejemplo siguiente se usa el `_` carácter para agrupar un literal binario en grupos de 8 bits:</span><span class="sxs-lookup"><span data-stu-id="09fcc-156">The following example uses the `_` character to group a binary literal into 8-bit groups:</span></span>

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

<span data-ttu-id="09fcc-157">Puede seguir un literal con prefijo con un carácter de tipo literal.</span><span class="sxs-lookup"><span data-stu-id="09fcc-157">You can follow a prefixed literal with a literal type character.</span></span> <span data-ttu-id="09fcc-158">Esto se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="09fcc-158">The following example shows this.</span></span>

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

<span data-ttu-id="09fcc-159">En el ejemplo anterior, `counter` tiene el valor decimal de-32768 y `flags` tiene el valor decimal de + 32768.</span><span class="sxs-lookup"><span data-stu-id="09fcc-159">In the previous example, `counter` has the decimal value of -32768, and `flags` has the decimal value of +32768.</span></span>

<span data-ttu-id="09fcc-160">A partir de Visual Basic 15,5, también puede usar el carácter de subrayado ( `_` ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales.</span><span class="sxs-lookup"><span data-stu-id="09fcc-160">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="09fcc-161">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="09fcc-161">For example:</span></span>

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a><span data-ttu-id="09fcc-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="09fcc-162">See also</span></span>

- [<span data-ttu-id="09fcc-163">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="09fcc-163">Data Types</span></span>](index.md)
- [<span data-ttu-id="09fcc-164">Tipos de datos básicos</span><span class="sxs-lookup"><span data-stu-id="09fcc-164">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="09fcc-165">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="09fcc-165">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="09fcc-166">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="09fcc-166">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="09fcc-167">Solución de problemas de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="09fcc-167">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="09fcc-168">Declaración de variable</span><span class="sxs-lookup"><span data-stu-id="09fcc-168">Variable Declaration</span></span>](../variables/variable-declaration.md)
- [<span data-ttu-id="09fcc-169">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="09fcc-169">Data Types</span></span>](../../../language-reference/data-types/index.md)
