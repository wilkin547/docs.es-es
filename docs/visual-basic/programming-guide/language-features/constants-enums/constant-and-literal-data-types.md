---
title: Tipos de datos constantes y literales (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: 9db7fa3f36021a39fafe6cf3da5af7070f0b5b0d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582979"
---
# <a name="constant-and-literal-data-types-visual-basic"></a>Tipos de datos constantes y literales (Visual Basic)
Un literal es un valor que se expresa como en sí mismo en lugar de como el valor de una variable o el resultado de una expresión, como el número 3 o la cadena "Hello". Una constante es un nombre significativo que ocupa el lugar de un literal y mantiene este mismo valor en todo el programa, en lugar de una variable, cuyo valor puede cambiar.  
  
 Cuando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) es `Off` y [option STRICT](../../../../visual-basic/language-reference/statements/option-strict-statement.md) es `On`, debe declarar explícitamente todas las constantes con un tipo de datos. En el ejemplo siguiente, el tipo de datos de `MyByte` se declara explícitamente como tipo de datos `Byte`:  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 Cuando `Option Infer` se `On` o se `Off` `Option Strict`, puede declarar una constante sin especificar un tipo de datos con una cláusula `As`. El compilador determina el tipo de la constante a partir del tipo de la expresión. Un literal numérico entero se convierte de forma predeterminada en el tipo de datos `Integer`. El tipo de datos predeterminado para los números de punto flotante es `Double`, y las palabras clave `True` y `False` especificar una constante de `Boolean`.  
  
## <a name="literals-and-type-coercion"></a>Literales y coerción de tipos  
 En algunos casos, puede que desee forzar un literal a un tipo de datos determinado. por ejemplo, al asignar un valor literal entero especialmente grande a una variable de tipo `Decimal`. En el ejemplo siguiente se genera un error:  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 El error se produce a partir de la representación del literal. El tipo de datos `Decimal` puede contener un valor de gran tamaño, pero el literal se representa implícitamente como una `Long`, lo que no puede.  
  
 Puede forzar un literal a un tipo de datos determinado de dos maneras: anexando un carácter de tipo a él o colocándolo dentro de los caracteres envolventes. Un carácter de tipo o caracteres de cierre deben preceder o seguir inmediatamente al literal, sin espacios ni caracteres intermedios de ningún tipo.  
  
 Para que el ejemplo anterior funcione, puede anexar el carácter de tipo `D` al literal, lo que hace que se represente como un `Decimal`:  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 En el ejemplo siguiente se muestra el uso correcto de caracteres de tipo y caracteres de inclusión:  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 En la tabla siguiente se muestran los caracteres envolventes y los caracteres de tipo disponibles en Visual Basic.  
  
|Tipo de datos|Carácter envolvente|Carácter de tipo anexado|  
|---|---|---|  
|`Boolean`|(ninguno)|(ninguno)|  
|`Byte`|(ninguno)|(ninguno)|  
|`Char`|"|C|  
|`Date`|#|(ninguno)|  
|`Decimal`|(ninguno)|D o @|  
|`Double`|(ninguno)|R o #|  
|`Integer`|(ninguno)|I o%|  
|`Long`|(ninguno)|L o &|  
|`Short`|(ninguno)|S|  
|`Single`|(ninguno)|F o!|  
|`String`|"|(ninguno)|  
  
## <a name="see-also"></a>Vea también

- [Constantes definidas por el usuario](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)
- [Declarar una constante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)
- [Información general sobre las constantes](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Option Explicit (instrucción)](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Información general sobre las enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Cómo: declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Tipos de datos](../../../../visual-basic/language-reference/data-types/index.md)
- [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)
