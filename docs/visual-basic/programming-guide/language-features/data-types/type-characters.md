---
title: Escriba los caracteres (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals
- F literal type character
- '& identifier type character'
- type characters
- octal literals
- literals, hexadecimal
- '&O prefix for octal values'
- literals, default types
- defaults, literal types
- C literal type character
- type characters, literal
- $ identifier type character
- L literal type character
- UI literal type characters
- default literal types
- D literal type character
- literals, octal
- S literal type character
- '! identifier type character'
- US literal type characters
- '% identifier type character'
- data types [Visual Basic], type characters
- characters, identifier type
- type characters, identifier
- '# identifier type character'
- identifier type characters
- literal type characters
- I literal type character
- R literal type character
- '@ identifier type character'
- UL literal type characters
- literal types, default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6e112e7d221ef8e7a660094306bbb242c988e843
ms.lasthandoff: 03/13/2017

---
# <a name="type-characters-visual-basic"></a>Caracteres de tipo (Visual Basic)
Además de especificar un tipo de datos en una instrucción de declaración, puede forzar el tipo de datos de algunos elementos de programación con un *carácter de tipo*. El carácter de tipo debe seguir inmediatamente el elemento, sin ningún tipo de carácter intermedio.  
  
 El carácter de tipo no es parte del nombre del elemento. Puede hacer referencia a un elemento definido con un carácter de tipo sin el carácter de tipo.  
  
## <a name="identifier-type-characters"></a>Caracteres de tipo identificador  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Proporciona un conjunto de *caracteres de tipo identificador*, que puede utilizar en una declaración para especificar el tipo de datos de una variable o constante. En la tabla siguiente muestra los caracteres de tipo identificador disponibles con ejemplos de uso.  
  
|Carácter de tipo identificador|Tipo de datos|Ejemplo|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 No existe ningún carácter de tipo de identificador para la `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, o `UShort` tipos de datos, ni para los tipos de datos compuestos como matrices o estructuras.  
  
 En algunos casos, puede anexar el `$` caracteres para un [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] funcione, por ejemplo `Left$` en lugar de `Left`, para obtener un valor devuelto de tipo `String`.  
  
 En todos los casos, el carácter de tipo identificador debe seguir inmediatamente el nombre del identificador.  
  
## <a name="literal-type-characters"></a>Caracteres de tipo literal  
 Un *literal* es una representación textual de un valor concreto de un tipo de datos.  
  
### <a name="default-literal-types"></a>Tipos literales predeterminados  
 El formato de un literal tal como aparece en el código normalmente determina el tipo de datos. La siguiente tabla muestra estos tipos predeterminados.  
  
|Formato textual de literal|Tipo de datos predeterminado|Ejemplo|  
|-----------------------------|-----------------------|-------------|  
|Numérico, ninguna parte fraccionaria|`Integer`|`2147483647`|  
|Numérico, ninguna parte fraccionaria, demasiado grande para`Integer`|`Long`|`2147483648`|  
|Numérico, parte fraccionaria|`Double`|`1.2`|  
|Entre comillas dobles|`String`|`"A"`|  
|Delimitado por signos de número|`Date`|`#5/17/1993 9:32 AM#`|  
  
### <a name="forced-literal-types"></a>Tipo de literales forzados  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Proporciona un conjunto de *caracteres de tipo literal*, que puede utilizar para forzar que un literal adopte un tipo de datos distinto de su forma indica. Para ello, anexe el carácter al final del literal. La siguiente tabla muestra los caracteres de tipo literal disponibles con ejemplos de uso.  
  
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
  
 No existe ningún carácter de tipo literal para la `Boolean`, `Byte`, `Date`, `Object`, `SByte`, o `String` tipos de datos, ni para los tipos de datos compuestos como matrices o estructuras.  
  
 Los literales también pueden utilizar los caracteres de tipo identificador (`%`, `&`, `@`, `!`, `#`, `$`), como variables, constantes y expresiones. Sin embargo, el literal de tipo caracteres (`S`, `I`, `L`, `D`, `F`, `R`, `C`) puede usarse sólo con literales.  
  
 En todos los casos, el carácter de tipo literal debe seguir inmediatamente el valor literal.  
  
## <a name="hexadecimal-and-octal-literals"></a>Literales octales y hexadecimales  
 El compilador traduce normalmente un literal entero para estar en el sistema numérico decimal (base 10). Se puede forzar un literal entero sea hexadecimal (base 16) con el `&H` prefijo y se puede forzar que sea octal (base 8) con el `&O` prefijo. Los dígitos que siguen el prefijo deben ser adecuados para el sistema numérico. Esto ilustra en la tabla siguiente.  
  
|Base numérica|Prefijo|Valores de dígitos válidos|Ejemplo|  
|-----------------|------------|------------------------|-------------|  
|Hexadecimal (base 16)|`&H`|0-9 y A-f|`&HFFFF`|  
|Octal (base 8)|`&O`|0-7|`&O77`|  
  
 Puede agregar un literal prefijado con un carácter de tipo literal. En el ejemplo siguiente se muestra cómo hacerlo.  
  
```  
Dim counter As Short = &H8000S  
Dim flags As UShort = &H8000US  
```  
  
 En el ejemplo anterior, `counter` tiene el valor decimal de -32768, y `flags` tiene el valor decimal de +&32768;.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Tipos de datos elementales](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
