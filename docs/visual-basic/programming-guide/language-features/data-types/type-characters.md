---
description: 'Más información sobre: caracteres de tipo (Visual Basic)'
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
ms.openlocfilehash: d1afccb821d2ffb4dfabe3c38e0db4a7f902c164
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100454552"
---
# <a name="type-characters-visual-basic"></a><span data-ttu-id="e95b4-103">Caracteres de tipo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e95b4-103">Type characters (Visual Basic)</span></span>

<span data-ttu-id="e95b4-104">Además de especificar un tipo de datos en una instrucción de declaración, puede forzar el tipo de datos de algunos elementos de programación con un *carácter de tipo*.</span><span class="sxs-lookup"><span data-stu-id="e95b4-104">In addition to specifying a data type in a declaration statement, you can force the data type of some programming elements with a *type character*.</span></span> <span data-ttu-id="e95b4-105">El carácter de tipo debe ir inmediatamente después del elemento, sin caracteres intermedios de ningún tipo.</span><span class="sxs-lookup"><span data-stu-id="e95b4-105">The type character must immediately follow the element, with no intervening characters of any kind.</span></span>

<span data-ttu-id="e95b4-106">El carácter de tipo no forma parte del nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="e95b4-106">The type character is not part of the name of the element.</span></span> <span data-ttu-id="e95b4-107">Se puede hacer referencia a un elemento definido con un carácter de tipo sin el carácter de tipo.</span><span class="sxs-lookup"><span data-stu-id="e95b4-107">An element defined with a type character can be referenced without the type character.</span></span>

## <a name="identifier-type-characters"></a><span data-ttu-id="e95b4-108">Caracteres de tipo de identificador</span><span class="sxs-lookup"><span data-stu-id="e95b4-108">Identifier type characters</span></span>

<span data-ttu-id="e95b4-109">Visual Basic proporciona un conjunto de *caracteres de tipo de identificador* que puede usar en una declaración para especificar el tipo de datos de una variable o constante.</span><span class="sxs-lookup"><span data-stu-id="e95b4-109">Visual Basic supplies a set of *identifier type characters* that you can use in a declaration to specify the data type of a variable or constant.</span></span> <span data-ttu-id="e95b4-110">En la tabla siguiente se muestran los caracteres de tipo de identificador disponibles con ejemplos de uso.</span><span class="sxs-lookup"><span data-stu-id="e95b4-110">The following table shows the available identifier type characters with examples of usage.</span></span>
  
|<span data-ttu-id="e95b4-111">Carácter de tipo de identificador</span><span class="sxs-lookup"><span data-stu-id="e95b4-111">Identifier type character</span></span>|<span data-ttu-id="e95b4-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e95b4-112">Data type</span></span>|<span data-ttu-id="e95b4-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e95b4-113">Example</span></span>|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 <span data-ttu-id="e95b4-114">No existen caracteres de tipo identificador para los `Boolean` tipos de datos,,,,,,,, `Byte` `Char` `Date` `Object` `SByte` `Short` `UInteger` `ULong` o `UShort` , ni para los tipos de datos compuestos como matrices o estructuras.</span><span class="sxs-lookup"><span data-stu-id="e95b4-114">No identifier type characters exist for the `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="e95b4-115">En algunos casos, puede anexar el `$` carácter a una Visual Basic función, por ejemplo, en `Left$` lugar de `Left` , para obtener un valor devuelto de tipo `String` .</span><span class="sxs-lookup"><span data-stu-id="e95b4-115">In some cases, you can append the `$` character to a Visual Basic function, for example `Left$` instead of `Left`, to obtain a returned value of type `String`.</span></span>

<span data-ttu-id="e95b4-116">En todos los casos, el carácter de tipo de identificador debe aparecer inmediatamente después del nombre del identificador.</span><span class="sxs-lookup"><span data-stu-id="e95b4-116">In all cases, the identifier type character must immediately follow the identifier name.</span></span>

## <a name="literal-type-characters"></a><span data-ttu-id="e95b4-117">Caracteres de tipo literal</span><span class="sxs-lookup"><span data-stu-id="e95b4-117">Literal type characters</span></span>

<span data-ttu-id="e95b4-118">Un *literal* es una representación textual de un valor determinado de un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="e95b4-118">A *literal* is a textual representation of a particular value of a data type.</span></span>  

### <a name="default-literal-types"></a><span data-ttu-id="e95b4-119">Tipos literales predeterminados</span><span class="sxs-lookup"><span data-stu-id="e95b4-119">Default literal types</span></span>

<span data-ttu-id="e95b4-120">La forma de un literal tal como aparece en el código suele determinar su tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="e95b4-120">The form of a literal as it appears in your code ordinarily determines its data type.</span></span> <span data-ttu-id="e95b4-121">En la tabla siguiente se muestran estos tipos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="e95b4-121">The following table shows these default types.</span></span>  
  
|<span data-ttu-id="e95b4-122">Forma textual de literal</span><span class="sxs-lookup"><span data-stu-id="e95b4-122">Textual form of literal</span></span>|<span data-ttu-id="e95b4-123">Tipo de datos predeterminado</span><span class="sxs-lookup"><span data-stu-id="e95b4-123">Default data type</span></span>|<span data-ttu-id="e95b4-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e95b4-124">Example</span></span>|  
|-----------------------------|-----------------------|-------------|  
|<span data-ttu-id="e95b4-125">Numeric, sin parte fraccionaria</span><span class="sxs-lookup"><span data-stu-id="e95b4-125">Numeric, no fractional part</span></span>|`Integer`|`2147483647`|  
|<span data-ttu-id="e95b4-126">Numérico, sin parte fraccionaria, demasiado grande para `Integer`</span><span class="sxs-lookup"><span data-stu-id="e95b4-126">Numeric, no fractional part, too large for `Integer`</span></span>|`Long`|`2147483648`|  
|<span data-ttu-id="e95b4-127">Numeric, parte fraccionaria</span><span class="sxs-lookup"><span data-stu-id="e95b4-127">Numeric, fractional part</span></span>|`Double`|`1.2`|  
|<span data-ttu-id="e95b4-128">Entre comillas dobles</span><span class="sxs-lookup"><span data-stu-id="e95b4-128">Enclosed in double quotation marks</span></span>|`String`|`"A"`|  
|<span data-ttu-id="e95b4-129">Entre signos de número</span><span class="sxs-lookup"><span data-stu-id="e95b4-129">Enclosed within number signs</span></span>|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a><span data-ttu-id="e95b4-130">Tipos de literales forzados</span><span class="sxs-lookup"><span data-stu-id="e95b4-130">Forced literal types</span></span>

<span data-ttu-id="e95b4-131">Visual Basic proporciona un conjunto de *caracteres de tipo literal*, que puede usar para forzar que un literal asuma un tipo de datos distinto del que indica su forma.</span><span class="sxs-lookup"><span data-stu-id="e95b4-131">Visual Basic supplies a set of *literal type characters*, which you can use to force a literal to assume a data type other than the one its form indicates.</span></span> <span data-ttu-id="e95b4-132">Para ello, Anexe el carácter al final del literal.</span><span class="sxs-lookup"><span data-stu-id="e95b4-132">You do this by appending the character to the end of the literal.</span></span> <span data-ttu-id="e95b4-133">En la tabla siguiente se muestran los caracteres de tipo literal disponibles con ejemplos de uso.</span><span class="sxs-lookup"><span data-stu-id="e95b4-133">The following table shows the available literal type characters with examples of usage.</span></span>
  
|<span data-ttu-id="e95b4-134">Carácter de tipo literal</span><span class="sxs-lookup"><span data-stu-id="e95b4-134">Literal type character</span></span>|<span data-ttu-id="e95b4-135">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e95b4-135">Data type</span></span>|<span data-ttu-id="e95b4-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e95b4-136">Example</span></span>|  
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

<span data-ttu-id="e95b4-137">No existen caracteres de tipo literal para `Boolean` los `Byte` tipos de datos,, `Date` ,, `Object` `SByte` o `String` , ni para los tipos de datos compuestos como matrices o estructuras.</span><span class="sxs-lookup"><span data-stu-id="e95b4-137">No literal type characters exist for the `Boolean`, `Byte`, `Date`, `Object`, `SByte`, or `String` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="e95b4-138">Los literales también pueden usar los caracteres de tipo de identificador ( `%` , `&` , `@` , `!` , `#` , `$` ), como pueden ser variables, constantes y expresiones.</span><span class="sxs-lookup"><span data-stu-id="e95b4-138">Literals can also use the identifier type characters (`%`, `&`, `@`, `!`, `#`, `$`), as can variables, constants, and expressions.</span></span> <span data-ttu-id="e95b4-139">Sin embargo, los caracteres de tipo literal ( `S` , `I` , `L` , `D` , `F` , `R` , `C` ) solo se pueden usar con literales.</span><span class="sxs-lookup"><span data-stu-id="e95b4-139">However, the literal type characters (`S`, `I`, `L`, `D`, `F`, `R`, `C`) can be used only with literals.</span></span>

<span data-ttu-id="e95b4-140">En todos los casos, el carácter de tipo literal debe seguir inmediatamente al valor literal.</span><span class="sxs-lookup"><span data-stu-id="e95b4-140">In all cases, the literal type character must immediately follow the literal value.</span></span>

## <a name="hexadecimal-binary-and-octal-literals"></a><span data-ttu-id="e95b4-141">Literales hexadecimales, binarios y octales</span><span class="sxs-lookup"><span data-stu-id="e95b4-141">Hexadecimal, binary, and octal literals</span></span>

<span data-ttu-id="e95b4-142">Normalmente, el compilador interpreta un literal entero para que esté en el sistema numérico decimal (base 10).</span><span class="sxs-lookup"><span data-stu-id="e95b4-142">The compiler normally interprets an integer literal to be in the decimal (base 10) number system.</span></span> <span data-ttu-id="e95b4-143">También puede definir un literal entero como un número hexadecimal (base 16) con el `&H` prefijo, como un número binario (base 2) con el `&B` prefijo, y como un número octal (base 8) con el `&O` prefijo.</span><span class="sxs-lookup"><span data-stu-id="e95b4-143">You can also define an integer literal as a hexadecimal (base 16) number with the `&H` prefix, as a binary (base 2) number with the `&B` prefix, and as an octal (base 8) number with the `&O` prefix.</span></span> <span data-ttu-id="e95b4-144">Los dígitos que siguen al prefijo deben ser adecuados para el sistema numérico.</span><span class="sxs-lookup"><span data-stu-id="e95b4-144">The digits that follow the prefix must be appropriate for the number system.</span></span> <span data-ttu-id="e95b4-145">En la tabla siguiente se muestra esto.</span><span class="sxs-lookup"><span data-stu-id="e95b4-145">The following table illustrates this.</span></span>  
  
|<span data-ttu-id="e95b4-146">Base numérica</span><span class="sxs-lookup"><span data-stu-id="e95b4-146">Number base</span></span>|<span data-ttu-id="e95b4-147">Prefijo</span><span class="sxs-lookup"><span data-stu-id="e95b4-147">Prefix</span></span>|<span data-ttu-id="e95b4-148">Valores de dígitos válidos</span><span class="sxs-lookup"><span data-stu-id="e95b4-148">Valid digit values</span></span>|<span data-ttu-id="e95b4-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e95b4-149">Example</span></span>|
|-----------------|------------|------------------------|-------------|
|<span data-ttu-id="e95b4-150">Hexadecimal (base 16)</span><span class="sxs-lookup"><span data-stu-id="e95b4-150">Hexadecimal (base 16)</span></span>|`&H`|<span data-ttu-id="e95b4-151">0-9 y A-F</span><span class="sxs-lookup"><span data-stu-id="e95b4-151">0-9 and A-F</span></span>|`&HFFFF`|
|<span data-ttu-id="e95b4-152">Binario (base 2)</span><span class="sxs-lookup"><span data-stu-id="e95b4-152">Binary (base 2)</span></span>|`&B`|<span data-ttu-id="e95b4-153">0-1</span><span class="sxs-lookup"><span data-stu-id="e95b4-153">0-1</span></span>|`&B01111100`|
|<span data-ttu-id="e95b4-154">Octal (base 8)</span><span class="sxs-lookup"><span data-stu-id="e95b4-154">Octal (base 8)</span></span>|`&O`|<span data-ttu-id="e95b4-155">0-7</span><span class="sxs-lookup"><span data-stu-id="e95b4-155">0-7</span></span>|`&O77`|

<span data-ttu-id="e95b4-156">A partir de Visual Basic 2017, puede usar el carácter de subrayado ( `_` ) como separador de grupos para mejorar la legibilidad de un literal entero.</span><span class="sxs-lookup"><span data-stu-id="e95b4-156">Starting in Visual Basic 2017, you can use the underscore character (`_`) as a group separator to enhance the readability of an integral literal.</span></span> <span data-ttu-id="e95b4-157">En el ejemplo siguiente se usa el `_` carácter para agrupar un literal binario en grupos de 8 bits:</span><span class="sxs-lookup"><span data-stu-id="e95b4-157">The following example uses the `_` character to group a binary literal into 8-bit groups:</span></span>

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

<span data-ttu-id="e95b4-158">Puede seguir un literal con prefijo con un carácter de tipo literal.</span><span class="sxs-lookup"><span data-stu-id="e95b4-158">You can follow a prefixed literal with a literal type character.</span></span> <span data-ttu-id="e95b4-159">Esto se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e95b4-159">The following example shows this.</span></span>

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

<span data-ttu-id="e95b4-160">En el ejemplo anterior, `counter` tiene el valor decimal de-32768 y `flags` tiene el valor decimal de + 32768.</span><span class="sxs-lookup"><span data-stu-id="e95b4-160">In the previous example, `counter` has the decimal value of -32768, and `flags` has the decimal value of +32768.</span></span>

<span data-ttu-id="e95b4-161">A partir de Visual Basic 15,5, también puede usar el carácter de subrayado ( `_` ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales.</span><span class="sxs-lookup"><span data-stu-id="e95b4-161">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="e95b4-162">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e95b4-162">For example:</span></span>

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a><span data-ttu-id="e95b4-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e95b4-163">See also</span></span>

- [<span data-ttu-id="e95b4-164">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e95b4-164">Data Types</span></span>](index.md)
- [<span data-ttu-id="e95b4-165">Tipos de datos básicos</span><span class="sxs-lookup"><span data-stu-id="e95b4-165">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="e95b4-166">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="e95b4-166">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="e95b4-167">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e95b4-167">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="e95b4-168">Solución de problemas de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="e95b4-168">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="e95b4-169">Declaración de variable</span><span class="sxs-lookup"><span data-stu-id="e95b4-169">Variable Declaration</span></span>](../variables/variable-declaration.md)
- [<span data-ttu-id="e95b4-170">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e95b4-170">Data Types</span></span>](../../../language-reference/data-types/index.md)
