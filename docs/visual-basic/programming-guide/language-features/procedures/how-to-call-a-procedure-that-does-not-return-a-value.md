---
title: "Cómo: Llamar a un procedimiento que no devuelve un valor (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bbea50132d1110b38bf9b01397795a2cd51f86d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Cómo: Llamar a un procedimiento que no devuelve un valor (Visual Basic)
A `Sub` procedimiento no devuelve un valor para el código de llamada. Se llama explícitamente con una instrucción llamada independiente. No se puede llamar a simplemente usando su nombre dentro de una expresión.  
  
### <a name="to-call-a-sub-procedure"></a>Llamar a un procedimiento Sub  
  
1.  Especifique el nombre de la `Sub` procedimiento.  
  
2.  Siga el nombre del procedimiento con paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis. Sin embargo, el uso de los paréntesis, el código será más fácil de leer.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de proporcionar los argumentos en el mismo orden que el `Sub` procedimiento define los parámetros correspondientes.  
  
     El ejemplo siguiente se llama el [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> función para activar una ventana de aplicación. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>toma el título de ventana como su único argumento. No devuelve ningún valor para el código de llamada. Si no se está ejecutando un proceso de Bloc de notas, en el ejemplo se inicia una <xref:System.ArgumentException>. El `Shell` procedimiento se da por supuesto que las aplicaciones están en las rutas de acceso especificadas.  
  
     [!code-vb[VbVbalrCatRef#11](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>  
 <xref:System.ArgumentException>  
 [Procedimientos](./index.md)  
 [Subprocedimientos](./sub-procedures.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Crear un procedimiento](./how-to-create-a-procedure.md)  
 [Llamar a un procedimiento que devuelve un valor](./how-to-call-a-procedure-that-returns-a-value.md)  
 [Cómo: llamar a un controlador de eventos en Visual Basic](./how-to-call-an-event-handler.md)
