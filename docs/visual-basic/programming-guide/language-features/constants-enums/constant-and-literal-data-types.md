---
title: "Tipos de datos constantes y literales (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "constantes, declarar"
  - "tipos de datos [Visual Basic], declarar"
  - "declaraciones, tipos de datos"
  - "declarar constantes, tipos de datos literales"
  - "declaraciones explícitas"
  - "literales, convertir un tipo de datos"
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Tipos de datos constantes y literales (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Un literal es un valor que se expresa a sí mismo en lugar de a un valor de variable o el resultado de una expresión, como el número 3 o la cadena "Hello".  Una constante es un nombre descriptivo que sustituye a un literal y retiene este mismo valor a lo largo del programa, lo que se opone a una variable cuyo valor puede cambiar.  
  
 Cuando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) es `Off` y [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) es `On`, debe declarar todas las constantes explícitamente con un tipo de datos.  En el siguiente ejemplo, el tipo de datos de `MyByte` se declara explícitamente como tipo de datos `Byte`:  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 Cuando `Option Infer` es `On` o `Option Strict` es `Off`, puede declarar una constante sin especificar un tipo de datos con una cláusula `As`.  El compilador determina el tipo de la constante del tipo de expresión.  Un literal entero numérico se convierte a tipo de datos `Integer` de manera predeterminada.  El tipo de datos predeterminado para números de punto flotante es `Double`, y las palabras clave `True` y `False` especifican una constante de tipo `Boolean`.  
  
## Literales y conversión de tipos  
 En algunos casos, puede que sea conveniente forzar un literal a un tipo de datos concreto, por ejemplo, al asignar un valor literal integral de gran tamaño a una variable de tipo `Decimal`.  El siguiente ejemplo produce un error:  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 El error tiene su origen en la representación del literal.  El tipo de datos `Decimal` puede contener un valor de este tamaño. Sin embargo, el literal se representa implícitamente como `Long`, lo que no es posible.  
  
 Se puede forzar la conversión de un literal a un tipo de datos concreto de dos maneras: agregándole un carácter de tipo o encerrándolo entre caracteres de inclusión.  El carácter de tipo o los caracteres de inclusión deben ir justo antes o a continuación del literal, sin ningún espacio o caracteres intermedios.  
  
 Para que funcione el ejemplo anterior, se anexa el carácter de tipo `D` al literal para que sea representado como un `Decimal`:  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 En el ejemplo siguiente se muestra la utilización correcta de los caracteres de tipo y de inclusión:  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 En la siguiente tabla se muestran los caracteres de inclusión y los caracteres de tipo disponibles en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
||||  
|-|-|-|  
|Tipo de datos|Carácter de inclusión|Carácter de tipo anexado|  
|`Boolean`|\(ninguno\)|\(ninguno\)|  
|`Byte`|\(ninguno\)|\(ninguno\)|  
|`Char`|"|C|  
|`Date`|\#|\(ninguno\)|  
|`Decimal`|\(ninguno\)|D o @|  
|`Double`|\(ninguno\)|R o \#|  
|`Integer`|\(ninguno\)|I o %|  
|`Long`|\(ninguno\)|L o &|  
|`Short`|\(ninguno\)|S|  
|`Single`|\(ninguno\)|F o \!|  
|`String`|"|\(ninguno\)|  
  
## Vea también  
 [Constantes definidas por el usuario](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)   
 [Cómo: Declarar una constante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)   
 [Información general sobre las constantes](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Option Explicit \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Información general sobre las enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Cómo: Declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)