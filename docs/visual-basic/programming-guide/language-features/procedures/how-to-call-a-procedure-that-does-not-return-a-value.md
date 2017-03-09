---
title: "C&#243;mo: Llamar a un procedimiento que no devuelve un valor (Visual Basic) | Microsoft Docs"
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
  - "llamadas a procedimientos, devolver valores"
  - "procedimientos, llamar"
  - "código de Visual Basic, procedimientos"
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# C&#243;mo: Llamar a un procedimiento que no devuelve un valor (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un procedimiento `Sub` no devuelve un valor al código de llamada.  Se llama a este procedimiento de forma explícita, con una instrucción de llamada independiente.  No se le puede llamar utilizando simplemente su nombre en una expresión.  
  
### Para llamar a un procedimiento Sub  
  
1.  Especifique el nombre del procedimiento de `Sub` .  
  
2.  Agregue paréntesis después del nombre del procedimiento para incluir entre ellos la lista de argumentos.  Si no hay ningún argumento, puede omitir opcionalmente los paréntesis.  Sin embargo, los paréntesis hacen que el código sea más fácil de leer.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis y separados por comas.  Asegúrese de proporcionar los argumentos en el mismo orden en que el procedimiento `Sub` define los parámetros correspondientes.  
  
     En el siguiente ejemplo, se llama a la función <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] para activar una ventana de la aplicación.  <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> toma el título de la ventana como único argumento.  No devuelve ningún valor al código de llamada.  Si no se está ejecutando un proceso del Bloc de notas, el ejemplo produce una excepción <xref:System.ArgumentException>.  En el procedimiento `Shell` se presupone que las aplicaciones se encuentran en las rutas de acceso especificadas.  
  
     [!code-vb[VbVbalrCatRef#11](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-call-a-procedure-_1_1.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>   
 <xref:System.ArgumentException>   
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Sub \(Instrucción\)](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Cómo: crear un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure.md)   
 [Cómo: Llamar a un procedimiento que devuelve un valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-returns-a-value.md)   
 [Cómo: Llamar a un controlador de eventos en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-event-handler.md)