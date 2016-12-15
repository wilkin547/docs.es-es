---
title: "C&#243;mo: Crear un procedimiento (Visual Basic) | Microsoft Docs"
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
  - "declaraciones de procedimientos"
  - "procedimientos, acerca de los procedimientos"
  - "procedimientos, definir"
  - "código de Visual Basic, procedimientos"
  - "código de Visual Basic, reutilizar"
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Crear un procedimiento (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Se incluye un procedimiento entre una instrucción de declaración de inicio \(`Sub` o `Function`\) y una instrucción de declaración de fin \(`End Sub` o `End Function`\).  Todo el código del procedimiento está incluido entre estas instrucciones.  
  
 Un procedimiento no puede contener otro procedimiento, por lo que sus instrucciones de inicio y de fin deben estar fuera de cualquier otro procedimiento.  
  
 Si tiene un código que realiza la misma tarea en distintos lugares, puede escribir la tarea una vez como procedimiento y llamarlo después desde distintos lugares del código.  
  
### Para crear un procedimiento que no devuelve un valor  
  
1.  Fuera de cualquier otro procedimiento, utilice una instrucción `Sub`, seguida de una instrucción `End Sub`.  
  
2.  En la instrucción `Sub`, agregue detrás de la palabra clave `Sub` el nombre del procedimiento y, a continuación, la lista de parámetros entre paréntesis.  
  
3.  Coloque las instrucciones del código del procedimiento entre las instrucciones `Sub` y `End Sub`  
  
### Para crear un procedimiento que devuelva un valor  
  
1.  Fuera de cualquier otro procedimiento, utilice una instrucción `Function`, seguida de una instrucción `End Function`.  
  
2.  En la instrucción `Function`, agregue detrás de la palabra clave `Function` el nombre del procedimiento y una cláusula `As` en la que se especifique el tipo de datos del valor devuelto.  
  
3.  Coloque las instrucciones de código del procedimiento entre las instrucciones `Function` y `End Function`.  
  
4.  Utilice una instrucción `Return` para devolver el valor al código de llamada.  
  
### Para conectar el nuevo procedimiento con los anteriores bloques de código repetitivos  
  
1.  Asegúrese de que define el nuevo procedimiento en un lugar donde el código anterior tiene acceso a él.  
  
2.  En el anterior bloque de código repetitivo, reemplace las instrucciones que realizan la tarea repetitiva por una única instrucción que llama al procedimiento `Sub` o `Function`.  
  
3.  Si el procedimiento es una `Function` que devuelve un valor, asegúrese de que la instrucción de llamada realiza una acción con el valor devuelto, como almacenarlo en una variable o, de lo contrario, se perderá el valor.  
  
## Ejemplo  
 El siguiente procedimiento `Function` calcula la hipotenusa de un triángulo rectángulo a partir de los valores de los catetos.  
  
 [!code-vb[VbVbcnProcedures#1](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-create-a-procedure_1.vb)]  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Procedimientos Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedimientos de operador](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Procedimientos recursivos](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Programación orientada a objetos](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)