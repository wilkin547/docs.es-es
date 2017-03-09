---
title: "C&#243;mo: Crear un procedimiento que devuelve un valor (Visual Basic) | Microsoft Docs"
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
  - "procedimientos, definir"
  - "procedimientos, devolver un valor"
  - "código de Visual Basic, procedimientos"
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# C&#243;mo: Crear un procedimiento que devuelve un valor (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Utiliza un procedimiento `Function` para devolver un valor al código de llamada.  
  
### Para crear un procedimiento que devuelva un valor  
  
1.  Fuera de cualquier otro procedimiento, utilice una instrucción `Function`, seguida de una instrucción `End Function`.  
  
2.  En la instrucción `Function`, siga la palabra clave `Function` con el nombre del procedimiento y a continuación la lista de parámetros entre paréntesis.  
  
3.  A continuación de paréntesis incluya una cláusula `As` para especificar el tipo de datos del valor devuelto.  
  
4.  Coloque las instrucciones de código del procedimiento entre las instrucciones `Function` y `End Function`.  
  
5.  Utilice una instrucción `Return` para devolver el valor al código de llamada.  
  
     El siguiente procedimiento `Function` calcula la hipotenusa de un triángulo rectángulo a partir de los valores de los catetos.  
  
     [!code-vb[VbVbcnProcedures#1](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-create-a-procedur_1.vb)]  
  
     El ejemplo siguiente muestra una llamada típica a  `hypotenuse`.  
  
     [!code-vb[VbVbcnProcedures#6](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-create-a-procedur_2.vb)]  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedimientos de operador](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Function \(Instrucción\)](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Cómo: Devolver un valor de un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-return-a-value-from-a-procedure.md)   
 [Cómo: Llamar a un procedimiento que devuelve un valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-returns-a-value.md)