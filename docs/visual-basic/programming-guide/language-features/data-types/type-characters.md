---
title: Caracteres de tipo (Visual Basic)
ms.custom: 
ms.date: 01/31/2018
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
author: rpetrusha
ms.author: ronpet
ms.manager: wpickett
ms.openlocfilehash: bdb675b9605d03829c95897382daa6d03cf1b041
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
---
# <a name="type-characters-visual-basic"></a><span data-ttu-id="c5cb6-102">Escriba los caracteres (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5cb6-102">Type characters (Visual Basic)</span></span>

<span data-ttu-id="c5cb6-103">Además de especificar un tipo de datos en una instrucción de declaración, puede forzar el tipo de datos de algunos elementos de programación con un *carácter de tipo*.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-103">In addition to specifying a data type in a declaration statement, you can force the data type of some programming elements with a *type character*.</span></span> <span data-ttu-id="c5cb6-104">El carácter de tipo debe aparecer inmediatamente después del elemento, sin los caracteres de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-104">The type character must immediately follow the element, with no intervening characters of any kind.</span></span>

<span data-ttu-id="c5cb6-105">El carácter de tipo no forma parte del nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-105">The type character is not part of the name of the element.</span></span> <span data-ttu-id="c5cb6-106">Puede hacer referencia a un elemento definido con un carácter de tipo sin el carácter de tipo.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-106">An element defined with a type character can be referenced without the type character.</span></span>

## <a name="identifier-type-characters"></a><span data-ttu-id="c5cb6-107">Caracteres de tipo identificador</span><span class="sxs-lookup"><span data-stu-id="c5cb6-107">Identifier type characters</span></span>

<span data-ttu-id="c5cb6-108">Visual Basic proporciona un conjunto de *caracteres de tipo identificador* que puede utilizar en una declaración para especificar el tipo de datos de una variable o constante.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-108">Visual Basic supplies a set of *identifier type characters* that you can use in a declaration to specify the data type of a variable or constant.</span></span> <span data-ttu-id="c5cb6-109">La tabla siguiente muestran los caracteres de tipo identificador disponibles con ejemplos de uso.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-109">The following table shows the available identifier type characters with examples of usage.</span></span>
  
|<span data-ttu-id="c5cb6-110">Carácter de tipo identificador</span><span class="sxs-lookup"><span data-stu-id="c5cb6-110">Identifier type character</span></span>|<span data-ttu-id="c5cb6-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="c5cb6-111">Data type</span></span>|<span data-ttu-id="c5cb6-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5cb6-112">Example</span></span>|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 <span data-ttu-id="c5cb6-113">No existe ningún carácter de tipo de identificador para la `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, o `UShort` tipos de datos, o para ninguno tipos de datos compuestos como matrices o estructuras.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-113">No identifier type characters exist for the `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="c5cb6-114">En algunos casos, puede anexar el `$` carácter a una función de Visual Basic, por ejemplo `Left$` en lugar de `Left`, para obtener un valor devuelto de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-114">In some cases, you can append the `$` character to a Visual Basic function, for example `Left$` instead of `Left`, to obtain a returned value of type `String`.</span></span>

<span data-ttu-id="c5cb6-115">En todos los casos, el carácter de tipo identificador debe aparecer inmediatamente después del nombre del identificador.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-115">In all cases, the identifier type character must immediately follow the identifier name.</span></span>

## <a name="literal-type-characters"></a><span data-ttu-id="c5cb6-116">Caracteres de tipo literal</span><span class="sxs-lookup"><span data-stu-id="c5cb6-116">Literal type characters</span></span>

<span data-ttu-id="c5cb6-117">A *literal* es una representación textual de un valor determinado de un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-117">A *literal* is a textual representation of a particular value of a data type.</span></span>  

### <a name="default-literal-types"></a><span data-ttu-id="c5cb6-118">Tipos literales predeterminados</span><span class="sxs-lookup"><span data-stu-id="c5cb6-118">Default literal types</span></span>

<span data-ttu-id="c5cb6-119">El formato de un literal tal como aparece en el código normalmente determina el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-119">The form of a literal as it appears in your code ordinarily determines its data type.</span></span> <span data-ttu-id="c5cb6-120">En la tabla siguiente se muestra estos tipos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-120">The following table shows these default types.</span></span>  
  
|<span data-ttu-id="c5cb6-121">Formato de texto de literal</span><span class="sxs-lookup"><span data-stu-id="c5cb6-121">Textual form of literal</span></span>|<span data-ttu-id="c5cb6-122">Tipo de datos predeterminado</span><span class="sxs-lookup"><span data-stu-id="c5cb6-122">Default data type</span></span>|<span data-ttu-id="c5cb6-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5cb6-123">Example</span></span>|  
|-----------------------------|-----------------------|-------------|  
|<span data-ttu-id="c5cb6-124">Numérico, ninguna parte fraccionaria</span><span class="sxs-lookup"><span data-stu-id="c5cb6-124">Numeric, no fractional part</span></span>|`Integer`|`2147483647`|  
|<span data-ttu-id="c5cb6-125">Numérico, ninguna parte fraccionaria, demasiado grande para`Integer`</span><span class="sxs-lookup"><span data-stu-id="c5cb6-125">Numeric, no fractional part, too large for `Integer`</span></span>|`Long`|`2147483648`|  
|<span data-ttu-id="c5cb6-126">Numérico, parte fraccionaria</span><span class="sxs-lookup"><span data-stu-id="c5cb6-126">Numeric, fractional part</span></span>|`Double`|`1.2`|  
|<span data-ttu-id="c5cb6-127">Entre comillas dobles</span><span class="sxs-lookup"><span data-stu-id="c5cb6-127">Enclosed in double quotation marks</span></span>|`String`|`"A"`|  
|<span data-ttu-id="c5cb6-128">Delimitado por un signo de número</span><span class="sxs-lookup"><span data-stu-id="c5cb6-128">Enclosed within number signs</span></span>|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a><span data-ttu-id="c5cb6-129">Tipos literales forzados</span><span class="sxs-lookup"><span data-stu-id="c5cb6-129">Forced literal types</span></span>

<span data-ttu-id="c5cb6-130">Visual Basic proporciona un conjunto de *caracteres de tipo literal*, lo que puede utilizar para forzar que un literal adopte un tipo de datos distinto de aquél su forma indica.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-130">Visual Basic supplies a set of *literal type characters*, which you can use to force a literal to assume a data type other than the one its form indicates.</span></span> <span data-ttu-id="c5cb6-131">Para ello, anexe el carácter al final del literal.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-131">You do this by appending the character to the end of the literal.</span></span> <span data-ttu-id="c5cb6-132">La siguiente tabla muestra los caracteres de tipo literal disponibles con ejemplos de uso.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-132">The following table shows the available literal type characters with examples of usage.</span></span>
  
|<span data-ttu-id="c5cb6-133">Carácter de tipo literal</span><span class="sxs-lookup"><span data-stu-id="c5cb6-133">Literal type character</span></span>|<span data-ttu-id="c5cb6-134">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="c5cb6-134">Data type</span></span>|<span data-ttu-id="c5cb6-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5cb6-135">Example</span></span>|  
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

<span data-ttu-id="c5cb6-136">No existe ningún carácter de tipo literal para la `Boolean`, `Byte`, `Date`, `Object`, `SByte`, o `String` tipos de datos, ni para los tipos de datos compuestos como matrices o estructuras.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-136">No literal type characters exist for the `Boolean`, `Byte`, `Date`, `Object`, `SByte`, or `String` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="c5cb6-137">Los literales también pueden utilizar los caracteres de tipo identificador (`%`, `&`, `@`, `!`, `#`, `$`), tal y como hacen las variables, constantes y expresiones.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-137">Literals can also use the identifier type characters (`%`, `&`, `@`, `!`, `#`, `$`), as can variables, constants, and expressions.</span></span> <span data-ttu-id="c5cb6-138">Sin embargo, el literal de tipo de caracteres (`S`, `I`, `L`, `D`, `F`, `R`, `C`) puede utilizarse solo con literales.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-138">However, the literal type characters (`S`, `I`, `L`, `D`, `F`, `R`, `C`) can be used only with literals.</span></span>

<span data-ttu-id="c5cb6-139">En todos los casos, el carácter de tipo literal debe seguir inmediatamente el valor literal.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-139">In all cases, the literal type character must immediately follow the literal value.</span></span>

## <a name="hexadecimal-binary-and-octal-literals"></a><span data-ttu-id="c5cb6-140">Literales hexadecimales, binarios y octales</span><span class="sxs-lookup"><span data-stu-id="c5cb6-140">Hexadecimal, binary, and octal literals</span></span>

<span data-ttu-id="c5cb6-141">Normalmente, el compilador interpreta un literal entero para estar en el sistema numérico decimal (base 10).</span><span class="sxs-lookup"><span data-stu-id="c5cb6-141">The compiler normally interprets an integer literal to be in the decimal (base 10) number system.</span></span> <span data-ttu-id="c5cb6-142">También puede definir un literal entero como un número hexadecimal (base 16) con el `&H` prefijo, como un número binario (base 2) con el `&B` prefijo y como un octal (base 8) con el `&O` prefijo.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-142">You can also define an integer literal as a hexadecimal (base 16) number with the `&H` prefix, as a binary (base 2) number with the `&B` prefix, and as an octal (base 8) number with the `&O` prefix.</span></span> <span data-ttu-id="c5cb6-143">Los dígitos que siguen el prefijo deben ser adecuados para el sistema numérico.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-143">The digits that follow the prefix must be appropriate for the number system.</span></span> <span data-ttu-id="c5cb6-144">Esto ilustra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-144">The following table illustrates this.</span></span>  
  
|<span data-ttu-id="c5cb6-145">Base numérica</span><span class="sxs-lookup"><span data-stu-id="c5cb6-145">Number base</span></span>|<span data-ttu-id="c5cb6-146">Prefijo</span><span class="sxs-lookup"><span data-stu-id="c5cb6-146">Prefix</span></span>|<span data-ttu-id="c5cb6-147">Valores de dígitos válidos</span><span class="sxs-lookup"><span data-stu-id="c5cb6-147">Valid digit values</span></span>|<span data-ttu-id="c5cb6-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5cb6-148">Example</span></span>|
|-----------------|------------|------------------------|-------------|
|<span data-ttu-id="c5cb6-149">Hexadecimal (base 16)</span><span class="sxs-lookup"><span data-stu-id="c5cb6-149">Hexadecimal (base 16)</span></span>|`&H`|<span data-ttu-id="c5cb6-150">0-9 y A-F</span><span class="sxs-lookup"><span data-stu-id="c5cb6-150">0-9 and A-F</span></span>|`&HFFFF`|
|<span data-ttu-id="c5cb6-151">Formato binario (base 2)</span><span class="sxs-lookup"><span data-stu-id="c5cb6-151">Binary (base 2)</span></span>|`0B`|<span data-ttu-id="c5cb6-152">0-1</span><span class="sxs-lookup"><span data-stu-id="c5cb6-152">0-1</span></span>|`&B01111100`|
|<span data-ttu-id="c5cb6-153">Octal (base 8)</span><span class="sxs-lookup"><span data-stu-id="c5cb6-153">Octal (base 8)</span></span>|`&O`|<span data-ttu-id="c5cb6-154">0-7</span><span class="sxs-lookup"><span data-stu-id="c5cb6-154">0-7</span></span>|`&O77`|

<span data-ttu-id="c5cb6-155">A partir de 2017 de Visual Basic, puede usar el carácter de subrayado (`_`) como separador de grupos para mejorar la legibilidad de un literal entero.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-155">Starting in Visual Basic 2017, you can use the underscore character (`_`) as a group separator to enhance the readability of an integral literal.</span></span> <span data-ttu-id="c5cb6-156">En el ejemplo siguiente se usa el `_` carácter que se va a agrupar un literal binario en grupos de 8 bits:</span><span class="sxs-lookup"><span data-stu-id="c5cb6-156">The following example uses the `_` character to group a binary literal into 8-bit groups:</span></span>

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

<span data-ttu-id="c5cb6-157">Puede agregar un literal prefijado con un carácter de tipo literal.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-157">You can follow a prefixed literal with a literal type character.</span></span> <span data-ttu-id="c5cb6-158">En el ejemplo siguiente se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-158">The following example shows this.</span></span>

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

<span data-ttu-id="c5cb6-159">En el ejemplo anterior, `counter` tiene el valor decimal entre-32768 y, y `flags` tiene el valor decimal de + 32768.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-159">In the previous example, `counter` has the decimal value of -32768, and `flags` has the decimal value of +32768.</span></span>

<span data-ttu-id="c5cb6-160">A partir de Visual Basic 15,5, también puede utilizar el carácter de subrayado (`_`) como separador inicial entre el prefijo y los dígitos hexadecimales, octales o binarios.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-160">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="c5cb6-161">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c5cb6-161">For example:</span></span>

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a><span data-ttu-id="c5cb6-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5cb6-162">See Also</span></span>

 [<span data-ttu-id="c5cb6-163">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="c5cb6-163">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="c5cb6-164">Tipos de datos básicos</span><span class="sxs-lookup"><span data-stu-id="c5cb6-164">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="c5cb6-165">Tipos de valores y tipos de referencias</span><span class="sxs-lookup"><span data-stu-id="c5cb6-165">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="c5cb6-166">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c5cb6-166">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="c5cb6-167">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="c5cb6-167">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="c5cb6-168">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="c5cb6-168">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="c5cb6-169">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="c5cb6-169">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
