---
title: "C&#243;mo: Obtener un valor de una propiedad (Visual Basic) | Microsoft Docs"
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
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# C&#243;mo: Obtener un valor de una propiedad (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Recupera el valor de una propiedad incluyendo el nombre de propiedad en una expresión.  
  
 El procedimiento `Get` de la propiedad recupera el valor pero no se le llama explícitamente por su nombre.  La propiedad se usa de la misma manera que una variable.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] realiza las llamadas a los procedimientos de la propiedad.  
  
### Para recuperar un valor de una propiedad  
  
1.  Utilice el nombre de la propiedad en una expresión del mismo modo que utilizaría el nombre de una variable.  Las propiedades pueden utilizarse en los mismos lugares que las variables o las constantes.  
  
     O bien  
  
     Utilice el nombre de propiedad detrás del signo igual \(`=`\) en una instrucción de asignación.  
  
     En el ejemplo siguiente se lee el valor de la propiedad `Now` de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], y se llama implícitamente a su procedimiento `Get`.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]  
  
2.  Si la propiedad toma argumentos, agregue paréntesis a continuación del nombre de la propiedad para incluir entre ellos la lista de argumentos.  Si no hay ningún argumento, puede omitir opcionalmente los paréntesis.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis y separados por comas.  Asegúrese de proporcionar los argumentos en el mismo orden en que la propiedad define los parámetros correspondientes.  
  
 El valor de la variable participa en la expresión del mismo modo que una variable o una constante, o se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property \(Instrucción\)](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Diferencias entre propiedades y variables en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Cómo: Crear una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [Cómo: Declarar una propiedad con niveles de acceso mixtos](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [Cómo: Llamar a un procedimiento de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [Cómo: Establecer un valor en una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)