---
title: "C&#243;mo: Llamar a un procedimiento de propiedad (Visual Basic) | Microsoft Docs"
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
  - "llamadas a procedimientos, procedimientos de propiedades"
  - "procedimientos, llamar"
  - "propiedades [Visual Basic], procedimientos de propiedades"
  - "código de Visual Basic, procedimientos"
  - "código de Visual Basic, propiedades"
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# C&#243;mo: Llamar a un procedimiento de propiedad (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Cuando se almacena un valor en una propiedad o cuando se recupera el valor de una propiedad, se llama a un procedimiento de dicha propiedad.  El acceso a una propiedad se obtiene del mismo modo que el acceso a una variable.  
  
 El procedimiento `Set` de la propiedad almacena un valor y el procedimiento `Get` recupera dicho valor.  Sin embargo, no se llama explícitamente a estos procedimientos.  La propiedad se usa en una expresión o instrucción de asignación del mismo modo que se almacena o se recupera el valor de una variable.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] realiza las llamadas a los procedimientos de la propiedad.  
  
### Para llamar al procedimiento Get de una propiedad  
  
1.  Utilice el nombre de la propiedad en una expresión del mismo modo que utilizaría el nombre de una variable.  Las propiedades pueden utilizarse en los mismos lugares que las variables o las constantes.  
  
     O bien  
  
     Utilice el nombre de propiedad detrás del signo igual \(`=`\) en una instrucción de asignación.  
  
     En el ejemplo siguiente se lee el valor de la propiedad <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>, y se llama implícitamente a su procedimiento `Get`.  
  
     [!code-vb[VbVbalrDateProperties#4](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/VbVbalrDateProperties/Module1.vb#4)]  
  
2.  Si la propiedad toma argumentos, agregue paréntesis a continuación del nombre de la propiedad para incluir entre ellos la lista de argumentos.  Si no hay ningún argumento, puede omitir opcionalmente los paréntesis.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis y separados por comas.  Asegúrese de proporcionar los argumentos en el mismo orden en que la propiedad define los parámetros correspondientes.  
  
 El valor de la variable participa en la expresión del mismo modo que una variable o una constante, o se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.  
  
### Para llamar al procedimiento Set de una propiedad  
  
1.  Utilice el nombre de propiedad en el lado izquierdo de una instrucción de asignación.  
  
     En el ejemplo siguiente se establece el valor de la propiedad <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>, y se llama implícitamente al procedimiento `Set`.  
  
     [!code-vb[VbVbcnProcedures#11](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-call-a-property-p_2.vb)]  
  
2.  Si la propiedad toma argumentos, agregue paréntesis a continuación del nombre de la propiedad para incluir entre ellos la lista de argumentos.  Si no hay ningún argumento, puede omitir opcionalmente los paréntesis.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis y separados por comas.  Asegúrese de proporcionar los argumentos en el mismo orden en que la propiedad define los parámetros correspondientes.  
  
 El valor generado en el lado derecho de la instrucción de asignación se almacena en la propiedad.  
  
## Vea también  
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property \(Instrucción\)](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Diferencias entre propiedades y variables en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Cómo: Crear una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [Cómo: Declarar una propiedad con niveles de acceso mixtos](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [Cómo: Establecer un valor en una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [Cómo: Obtener un valor de una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)   
 [Get \(Instrucción\)](../../../../visual-basic/language-reference/statements/get-statement.md)   
 [Set \(Instrucción\)](../../../../visual-basic/language-reference/statements/set-statement.md)