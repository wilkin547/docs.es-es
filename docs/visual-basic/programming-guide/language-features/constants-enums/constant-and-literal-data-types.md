---
title: Tipos de datos constantes y literales (Visual Basic) | Documentos de Microsoft
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
- declaring constants, literal data types
- data types [Visual Basic], declaring
- constants, declaring
- explicit declarations
- literals, coercing data type
- declarations, data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 22ad31415ab560b7fd0180a6dadd6d2dcd7ec77a
ms.lasthandoff: 03/13/2017

---
# <a name="constant-and-literal-data-types-visual-basic"></a>Tipos de datos constantes y literales (Visual Basic)
Un literal es un valor que se expresa como el propio en lugar de como valor de una variable o el resultado de una expresión, como el número 3 o la cadena "Hello". Una constante es un nombre significativo que toma el lugar de un literal y retiene este mismo valor en todo el programa, en lugar de una variable, cuyo valor puede cambiar.  
  
 Cuando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) es `Off` y [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) es `On`, debe declarar explícitamente todas las constantes con un tipo de datos. En el ejemplo siguiente, el tipo de datos de `MyByte` se declara explícitamente como tipo de datos `Byte`:  
  
 [!code-vb[1 VbVbalrConstants](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 Cuando `Option Infer` es `On` o `Option Strict` es `Off`, puede declarar una constante sin especificar un tipo de datos con un `As` cláusula. El compilador determina el tipo de la constante del tipo de la expresión. Un literal entero numérico se convierte de forma predeterminada para la `Integer` tipo de datos. Tipo de datos predeterminado para números de punto flotante es `Double`y las palabras clave `True` y `False` especificar un `Boolean` constante.  
  
## <a name="literals-and-type-coercion"></a>Literales y conversión de tipos  
 En algunos casos, puede forzar que un literal a un tipo de datos determinado; Por ejemplo, al asignar un valor literal integral especialmente grande a una variable de tipo `Decimal`. En el ejemplo siguiente, se produce un error:  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 Se produce el error de la representación del literal. El `Decimal` tipo de datos puede contener un valor de este tamaño, pero el literal se representa implícitamente como una `Long`, cuáles no.  
  
 Puede convertir un literal a un tipo de datos concreto de dos maneras: mediante la anexión de un carácter de tipo a él o colocando entre caracteres de inclusión. Un carácter de tipo o los caracteres de cierre inmediatamente deben antes o a continuación del literal, sin ningún espacio o caracteres intermedios de ningún tipo.  
  
 Para que funcione el ejemplo anterior, puede anexar el `D` escriba el carácter literal, lo que hace que se representa como un `Decimal`:  
  
 [!code-vb[VbVbalrConstants&#2;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 En el ejemplo siguiente se muestra el uso correcto de los caracteres de tipo y de inclusión:  
  
 [!code-vb[VbVbalrConstants&3;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 La siguiente tabla muestra los caracteres y el tipo envolvente caracteres disponibles en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
|Tipo de datos|Carácter de inclusión|Carácter de tipo anexado|  
|---|---|---|  
|`Boolean`|(ninguno)|(ninguno)|  
|`Byte`|(ninguno)|(ninguno)|  
|`Char`|"|C|  
|`Date`|#|(ninguno)|  
|`Decimal`|(ninguno)|D. o @|  
|`Double`|(ninguno)|R o #|  
|`Integer`|(ninguno)|I o %|  
|`Long`|(ninguno)|L o aspecto|  
|`Short`|(ninguno)|S|  
|`Single`|(ninguno)|F o!|  
|`String`|"|(ninguno)|  
  
## <a name="see-also"></a>Vea también  
 [Constantes definidas por el usuario](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)   
 [Cómo: declarar una constante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)   
 [Información general de constantes](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Option Explicit (instrucción)](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Información general de las enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Cómo: declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)
