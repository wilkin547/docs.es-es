---
title: "C&#243;mo: Establecer un valor en una propiedad (Visual Basic) | Microsoft Docs"
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
  - "propiedades [Visual Basic], valores"
  - "valores de propiedades"
  - "valores, propiedades"
  - "código de Visual Basic, procedimientos"
  - "código de Visual Basic, propiedades"
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# C&#243;mo: Establecer un valor en una propiedad (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Almacena un valor en una propiedad colocando el nombre de propiedad en el lado izquierdo de una instrucción de asignación.  
  
 El procedimiento `Set` de la propiedad almacena un valor, pero no se llama explícitamente por el nombre.  La propiedad se usa de la misma manera que una variable.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] realiza las llamadas a los procedimientos de la propiedad.  
  
### Para almacenar un valor en una propiedad  
  
1.  Utilice el nombre de propiedad en el lado izquierdo de una instrucción de asignación.  
  
     El ejemplo siguiente establece el valor de la propiedad `TimeOfDay` de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] en mediodía, llamando implícitamente a su procedimiento `Set`.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]  
  
2.  Si la propiedad toma argumentos, agregue paréntesis a continuación del nombre de la propiedad para incluir entre ellos la lista de argumentos.  Si no hay ningún argumento, puede omitir opcionalmente los paréntesis.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis y separados por comas.  Asegúrese de proporcionar los argumentos en el mismo orden en que la propiedad define los parámetros correspondientes.  
  
4.  El valor generado en el lado derecho de la instrucción de asignación se almacena en la propiedad.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>   
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property \(Instrucción\)](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Diferencias entre propiedades y variables en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Cómo: Crear una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [Cómo: Declarar una propiedad con niveles de acceso mixtos](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [Cómo: Llamar a un procedimiento de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [Cómo: Obtener un valor de una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)