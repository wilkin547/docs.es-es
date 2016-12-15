---
title: "Tipos de datos en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "tipos de datos [Visual Basic], declaración"
  - "establecimiento de tipos"
  - "tipos de datos [Visual Basic]"
  - "código de Visual Basic, tipos de datos"
  - "tipos de datos [Visual Basic], mejora de la velocidad"
ms.assetid: 5e1b9aaf-c7ca-4b29-9b22-0e82ed8e85e2
caps.latest.revision: 28
caps.handback.revision: 28
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Tipos de datos en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

El *tipo de datos* de un elemento de programación hace referencia al tipo de datos que puede contener y a cómo se almacenan dichos datos.  Los tipos de datos se aplican a todos los valores que pueden almacenarse en la memoria del equipo o participar en la evaluación de una expresión.  Cada variable, literal, constante, enumeración, propiedad, parámetro de procedimiento, argumento de procedimiento y valor devuelto por un procedimiento tiene un tipo de datos.  
  
## Tipos de datos declarados  
 Un elemento de programación se define con una instrucción de declaración y su tipo de datos se especifica con la cláusula `As`.  La tabla siguiente muestra las instrucciones utilizadas para declarar diversos elementos.  
  
|Elemento de programación|Declaración de tipos de datos|  
|------------------------------|-----------------------------------|  
|Variable|En una [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md)<br /><br /> `Dim`   `amount As Double`<br /><br /> `Static`   `yourName As String`<br /><br /> `Public`   `billsPaid As Decimal = 0`|  
|Literal|Con un carácter de tipo literal; vea "Caracteres de tipo literal" en [Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)<br /><br /> `Dim searchChar As Char = "."`  `C`|  
|Constante|En una [Const \(Instrucción\)](../../../../visual-basic/language-reference/statements/const-statement.md)<br /><br /> `Const`   `modulus As Single = 4.17825F`|  
|Enumeración|En una [Enum \(Instrucción\)](../../../../visual-basic/language-reference/statements/enum-statement.md)<br /><br /> `Public`   `Enum`   `colors`|  
|Propiedad|En una [Property \(Instrucción\)](../../../../visual-basic/language-reference/statements/property-statement.md)<br /><br /> `Property`   `region() As String`|  
|Parámetro de procedimiento|En una [Sub \(Instrucción\)](../../../../visual-basic/language-reference/statements/sub-statement.md), [Function \(Instrucción\)](../../../../visual-basic/language-reference/statements/function-statement.md) o [Operator \(Instrucción\)](../../../../visual-basic/language-reference/statements/operator-statement.md)<br /><br /> `Sub addSale(ByVal`   `amount`   `As Double)`|  
|Argumento de procedimiento|En el código de llamada; cada argumento es un elemento de programación que ya se ha declarado o una expresión que contiene los elementos declarados<br /><br /> `subString = Left(`  `inputString`  `,`   `5`  `)`|  
|Valor devuelto por procedimiento|En una [Function \(Instrucción\)](../../../../visual-basic/language-reference/statements/function-statement.md) o [Operator \(Instrucción\)](../../../../visual-basic/language-reference/statements/operator-statement.md)<br /><br /> `Function convert(ByVal b As Byte)`   `As String`|  
  
 Para obtener una lista de tipos de datos de Visual Basic, vea [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## Vea también  
 [Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Tipos de datos elementales](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Tipos genéricos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Uso eficiente de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)