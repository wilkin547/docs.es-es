---
title: "C&#243;mo: Devolver un valor de un procedimiento (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedimientos, devolver un valor"
  - "procedimientos, devolver"
  - "código de Visual Basic, procedimientos"
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# C&#243;mo: Devolver un valor de un procedimiento (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un procedimiento `Function` devuelve un valor al código de llamada ejecutando una instrucción  `Return` o encontrando una instrucción `Exit Function` o `End Function`  
  
### Para devolver un valor mediante la instrucción Return  
  
1.  Coloque una instrucción `Return` en el punto en el que finaliza la tarea del procedimiento.  
  
2.  Agregue detrás de la palabra clave `Return` una expresión que genere el valor que desea que se devuelva al código de llamada.  
  
3.  Puede tener más de una instrucción `Return` en el mismo procedimiento.  
  
     El siguiente procedimiento `Function` calcula la hipotenusa de un triángulo rectángulo y la devuelve al código de llamada.  
  
     [!code-vb[VbVbcnProcedures#1](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-return-a-value-fr_1.vb)]  
  
     El ejemplo siguiente muestra una llamada típica a `hypotenuse` que almacena el valor devuelto.  
  
     [!code-vb[VbVbcnProcedures#6](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-return-a-value-fr_2.vb)]  
  
### Para devolver un valor mediante Exit Function o End Function  
  
1.  En al menos un lugar del procedimiento `Function`, asigne un valor al nombre del procedimiento.  
  
2.  Al ejecutar una instrucción `Exit Function` o `End Function`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] devuelve el valor asignado más recientemente al nombre del procedimiento.  
  
3.  Puede tener más de una instrucción `Exit Function` en el mismo procedimiento, y puede mezclar las instrucciones `Return` y `Exit Function` en el mismo procedimiento.  
  
4.  Puede tener sólo una instrucción `End Function` en un procedimiento `Function`.  
  
     Para obtener más información y un ejemplo, vea "Valor devuelto" en [Function \(Instrucción\)](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedimientos de operador](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Function \(Instrucción\)](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Return \(Instrucción\)](../../../../visual-basic/language-reference/statements/return-statement.md)   
 [Cómo: Crear un procedimiento que devuelve un valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure-that-returns-a-value.md)   
 [Cómo: Llamar a un procedimiento que devuelve un valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-returns-a-value.md)