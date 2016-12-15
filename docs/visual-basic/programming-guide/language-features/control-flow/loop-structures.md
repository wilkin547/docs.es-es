---
title: "Estructuras de bucles (Visual Basic) | Microsoft Docs"
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
  - "instrucciones condicionales, estructuras de bucle"
  - "flujo de control, bucles"
  - "Do (instrucción), bucles Do"
  - "For (palabra clave) [Visual Basic], estructuras de bucle"
  - "estructuras de bucle"
  - "bucles"
  - "instrucciones [Visual Basic], bucle"
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Estructuras de bucles (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Las estructuras de bucles de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] permiten ejecutar una o varias líneas de código de forma repetitiva.  Puede repetir las instrucciones de una estructura de bucles hasta que una condición sea `True`, una condición sea `False`, un número de veces especificado o una vez para cada objeto de una colección.  
  
 En el siguiente ejemplo se muestra una estructura de bucle que ejecuta un conjunto de instrucciones hasta que una condición se convierta en verdadera.  
  
 ![Gráfico de flujo de un bucle Do...Until](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")  
Ejecutar un conjunto de instrucciones hasta que una condición se convierta en verdadera  
  
## Bucles While  
 La construcción `While`...`End While` ejecuta un conjunto de instrucciones mientras la condición especificada en la instrucción `While` sea `True`.  Para obtener más información, vea [While...End While \(Instrucción\)](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).  
  
## Bucles Do  
 La construcción `Do`...`Loop` le permite probar una condición al comienzo o al final de una estructura de bucle.  También puede especificar si repite el bucle mientras la condición sigue siendo `True` o hasta que se convierta en `True`.  Para obtener más información, vea [Do...Loop \(Instrucción\)](../../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## Bucles For  
 La construcción `For`...`Next` ejecuta el bucle un número fijo de veces.  Utiliza una variable de control de bucle, también denominada *contador* para realizar el seguimiento de las repeticiones.  Especifica los valores de inicio y fin de este contador, y puede especificar opcionalmente la cantidad en la que se incrementa de una repetición a la siguiente.  Para obtener más información, vea [For...Next \(Instrucción\)](../../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
## Bucles For Each  
 La construcción `For Each`...`Next` ejecuta un conjunto de instrucciones una vez para cada elemento de una colección.  Especifica la variable de control de bucle pero no tiene que determinar los valores de inicio y fin para ella.  Para obtener más información, vea [For Each...Next \(Instrucción\)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## Vea también  
 [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Estructuras de decisión](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Estructuras de control adicionales](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)   
 [Estructuras de control anidadas](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)