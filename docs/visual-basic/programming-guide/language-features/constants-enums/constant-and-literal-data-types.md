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
ms.openlocfilehash: 8d110ec17bcdb03f339d779b2950ba56d77957cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649853"
---
# <a name="constant-and-literal-data-types-visual-basic"></a>Tipos de datos constantes y literales (Visual Basic)
Un literal es un valor que se expresa por sí misma en lugar de como valor de una variable o el resultado de una expresión, como el número 3 o la cadena "Hello". Una constante es un nombre descriptivo que ocupa el lugar de un literal y retiene este mismo valor en todo el programa, en lugar de una variable, cuyo valor puede cambiar.  
  
 Cuando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) es `Off` y [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) es `On`, debe declarar explícitamente todas las constantes con un tipo de datos. En el ejemplo siguiente, el tipo de datos de `MyByte` se declara explícitamente como tipo de datos `Byte`:  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 Cuando `Option Infer` es `On` o `Option Strict` es `Off`, puede declarar una constante sin especificar un tipo de datos con un `As` cláusula. El compilador determina el tipo de la constante del tipo de la expresión. Un literal entero numérico se convierte de forma predeterminada para el `Integer` tipo de datos. Tipo de datos predeterminado para números de punto flotante es `Double`y las palabras clave `True` y `False` especificar un `Boolean` constante.  
  
## <a name="literals-and-type-coercion"></a>Literales y conversión de tipos  
 En algunos casos, puede forzar un literal a un tipo de datos determinado; Por ejemplo, al asignar un valor literal integral especialmente grande a una variable de tipo `Decimal`. En el ejemplo siguiente, se produce un error:  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 Los resultados de error de la representación del literal. El `Decimal` tipo de datos puede contener un valor tan grande, pero el literal se representa implícitamente como una `Long`, cuáles no.  
  
 Puede convertir un literal a un tipo de datos concreto de dos maneras: mediante la anexión de un carácter de tipo a él, o colocando entre caracteres de inclusión. Un carácter de tipo o incluye caracteres debe preceder inmediatamente o siga del literal, sin ningún espacio intermedio o caracteres de cualquier tipo.  
  
 Para que funcione el ejemplo anterior, puede anexar el `D` escribir caracteres en el literal, lo que hace que se representa como un `Decimal`:  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 En el ejemplo siguiente se muestra el uso correcto de los caracteres de tipo y caracteres de inclusión:  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 La siguiente tabla muestra los caracteres de inclusión y los caracteres de tipo disponibles en Visual Basic.  
  
|Tipo de datos|Carácter de inclusión|Carácter de tipo anexado|  
|---|---|---|  
|`Boolean`|(ninguno)|(ninguno)|  
|`Byte`|(ninguno)|(ninguno)|  
|`Char`|"|C|  
|`Date`|#|(ninguno)|  
|`Decimal`|(ninguno)|D. o @|  
|`Double`|(ninguno)|R o #|  
|`Integer`|(ninguno)|I o %|  
|`Long`|(ninguno)|L o &|  
|`Short`|(ninguno)|S|  
|`Single`|(ninguno)|F o!|  
|`String`|"|(ninguno)|  
  
## <a name="see-also"></a>Vea también  
 [Constantes definidas por el usuario](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)  
 [Declarar una constante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)  
 [Información general sobre las constantes](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Option Explicit (instrucción)](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Información general sobre las enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [Cómo: declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)
