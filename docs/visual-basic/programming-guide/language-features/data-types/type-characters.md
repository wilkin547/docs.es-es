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
# <a name="type-characters-visual-basic"></a>Caracteres de tipo (Visual Basic)

Además de especificar un tipo de datos en una instrucción de declaración, puede forzar el tipo de datos de algunos elementos de programación con un *carácter de tipo*. El carácter de tipo debe ir inmediatamente después del elemento, sin caracteres intermedios de ningún tipo.

El carácter de tipo no forma parte del nombre del elemento. Se puede hacer referencia a un elemento definido con un carácter de tipo sin el carácter de tipo.

## <a name="identifier-type-characters"></a>Caracteres de tipo de identificador

Visual Basic proporciona un conjunto de *caracteres de tipo de identificador* que puede usar en una declaración para especificar el tipo de datos de una variable o constante. En la tabla siguiente se muestran los caracteres de tipo de identificador disponibles con ejemplos de uso.
  
|Carácter de tipo de identificador|Tipo de datos|Ejemplo|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 No existen caracteres de tipo identificador para los `Boolean` tipos de datos,,,,,,,, `Byte` `Char` `Date` `Object` `SByte` `Short` `UInteger` `ULong` o `UShort` , ni para los tipos de datos compuestos como matrices o estructuras.

En algunos casos, puede anexar el `$` carácter a una Visual Basic función, por ejemplo, en `Left$` lugar de `Left` , para obtener un valor devuelto de tipo `String` .

En todos los casos, el carácter de tipo de identificador debe aparecer inmediatamente después del nombre del identificador.

## <a name="literal-type-characters"></a>Caracteres de tipo literal

Un *literal* es una representación textual de un valor determinado de un tipo de datos.  

### <a name="default-literal-types"></a>Tipos literales predeterminados

La forma de un literal tal como aparece en el código suele determinar su tipo de datos. En la tabla siguiente se muestran estos tipos predeterminados.  
  
|Forma textual de literal|Tipo de datos predeterminado|Ejemplo|  
|-----------------------------|-----------------------|-------------|  
|Numeric, sin parte fraccionaria|`Integer`|`2147483647`|  
|Numérico, sin parte fraccionaria, demasiado grande para `Integer`|`Long`|`2147483648`|  
|Numeric, parte fraccionaria|`Double`|`1.2`|  
|Entre comillas dobles|`String`|`"A"`|  
|Entre signos de número|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a>Tipos de literales forzados

Visual Basic proporciona un conjunto de *caracteres de tipo literal*, que puede usar para forzar que un literal asuma un tipo de datos distinto del que indica su forma. Para ello, Anexe el carácter al final del literal. En la tabla siguiente se muestran los caracteres de tipo literal disponibles con ejemplos de uso.
  
|Carácter de tipo literal|Tipo de datos|Ejemplo|  
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

No existen caracteres de tipo literal para `Boolean` los `Byte` tipos de datos,, `Date` ,, `Object` `SByte` o `String` , ni para los tipos de datos compuestos como matrices o estructuras.

Los literales también pueden usar los caracteres de tipo de identificador ( `%` , `&` , `@` , `!` , `#` , `$` ), como pueden ser variables, constantes y expresiones. Sin embargo, los caracteres de tipo literal ( `S` , `I` , `L` , `D` , `F` , `R` , `C` ) solo se pueden usar con literales.

En todos los casos, el carácter de tipo literal debe seguir inmediatamente al valor literal.

## <a name="hexadecimal-binary-and-octal-literals"></a>Literales hexadecimales, binarios y octales

Normalmente, el compilador interpreta un literal entero para que esté en el sistema numérico decimal (base 10). También puede definir un literal entero como un número hexadecimal (base 16) con el `&H` prefijo, como un número binario (base 2) con el `&B` prefijo, y como un número octal (base 8) con el `&O` prefijo. Los dígitos que siguen al prefijo deben ser adecuados para el sistema numérico. En la tabla siguiente se muestra esto.  
  
|Base numérica|Prefijo|Valores de dígitos válidos|Ejemplo|
|-----------------|------------|------------------------|-------------|
|Hexadecimal (base 16)|`&H`|0-9 y A-F|`&HFFFF`|
|Binario (base 2)|`&B`|0-1|`&B01111100`|
|Octal (base 8)|`&O`|0-7|`&O77`|

A partir de Visual Basic 2017, puede usar el carácter de subrayado ( `_` ) como separador de grupos para mejorar la legibilidad de un literal entero. En el ejemplo siguiente se usa el `_` carácter para agrupar un literal binario en grupos de 8 bits:

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

Puede seguir un literal con prefijo con un carácter de tipo literal. Esto se muestra en el ejemplo siguiente.

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

En el ejemplo anterior, `counter` tiene el valor decimal de-32768 y `flags` tiene el valor decimal de + 32768.

A partir de Visual Basic 15,5, también puede usar el carácter de subrayado ( `_` ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales. Por ejemplo:

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a>Consulte también

- [Tipo de datos](index.md)
- [Tipos de datos básicos](elementary-data-types.md)
- [Tipos de valor y tipos de referencia](value-types-and-reference-types.md)
- [Conversiones de tipos en Visual Basic](type-conversions.md)
- [Solución de problemas de los tipos de datos](troubleshooting-data-types.md)
- [Declaración de variable](../variables/variable-declaration.md)
- [Tipo de datos](../../../language-reference/data-types/index.md)
