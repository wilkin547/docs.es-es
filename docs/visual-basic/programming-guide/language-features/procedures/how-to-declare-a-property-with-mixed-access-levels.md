---
title: "C&#243;mo: Declarar una propiedad con niveles de acceso mixtos (Visual Basic) | Microsoft Docs"
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
  - "niveles de acceso, propiedades"
  - "niveles de acceso mixtos"
  - "procedimientos, definir"
  - "propiedades [Visual Basic], niveles de acceso"
  - "Property (instrucción), declarar niveles de acceso mixtos"
  - "código de Visual Basic, procedimientos"
  - "código de Visual Basic, propiedades"
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# C&#243;mo: Declarar una propiedad con niveles de acceso mixtos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Si desea que los procedimientos `Get` y `Set` de una propiedad tengan niveles de acceso distintos, puede utilizar el nivel más permisivo en la instrucción `Property` y el nivel más restrictivo en las instrucciones `Get` o `Set`.  Puede utilizar niveles de acceso mixtos en una propiedad cuando desee que ciertas partes del código puedan obtener el valor de la propiedad y que otras partes del código puedan modificar el valor.  
  
 Para obtener más información sobre los niveles de acceso, vea [Niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
### Para declarar una propiedad con niveles de acceso mixtos  
  
1.  Declare la propiedad de la manera habitual y especifique el nivel de acceso menos restrictivo \(por ejemplo, `Public`\) en la instrucción `Property`.  
  
2.  Declare el procedimiento `Get` o `Set` especificando el nivel de acceso más restrictivo \(por ejemplo, `Friend`\).  
  
3.  No especifique un nivel de acceso en el otro procedimiento de propiedad.  Se acepta el nivel de acceso declarado en la instrucción `Property`.  Puede restringir el acceso en un solo procedimiento de propiedad.  
  
     [!code-vb[VbVbcnProcedures#10](./codesnippet/VisualBasic/how-to-declare-a-property-with-mixed-access-levels_1.vb)]  
  
     En el ejemplo anterior, el procedimiento `Get` tiene el mismo acceso `Protected` que la propiedad, mientras que el procedimiento `Set` tiene acceso `Private`.  Una clase derivada de `employee` puede leer el valor `salary`, pero sólo la clase `employee` puede establecerlo.  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property \(Instrucción\)](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Diferencias entre propiedades y variables en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Cómo: Crear una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [Cómo: Llamar a un procedimiento de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [Cómo: Establecer un valor en una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [Cómo: Obtener un valor de una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)