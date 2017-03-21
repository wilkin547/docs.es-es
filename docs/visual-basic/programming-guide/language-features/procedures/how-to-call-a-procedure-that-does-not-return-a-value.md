---
title: "Cómo: llamar a un procedimiento que no devuelve un valor (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- procedure calls, returning values
- Visual Basic code, procedures
- procedures, calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 17b2b902f3ee6ab79b2614b7742aa08fefab2420
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Cómo: Llamar a un procedimiento que no devuelve un valor (Visual Basic)
Un `Sub` procedimiento devuelve un valor al código de llamada. Lo llama explícitamente con una instrucción de llamada independiente. No se puede llamar utilizando simplemente su nombre en una expresión.  
  
### <a name="to-call-a-sub-procedure"></a>Llamar a un procedimiento Sub  
  
1.  Especifique el nombre de la `Sub` procedimiento.  
  
2.  Siga el nombre del procedimiento con paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, se pueden omitir los paréntesis. Sin embargo, los paréntesis hacen el código más fácil de leer.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de proporcionar los argumentos en el mismo orden que el `Sub` procedimiento define los parámetros correspondientes.  
  
     El ejemplo siguiente se llama el [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>función para activar una ventana de la aplicación.</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>toma el título de la ventana como único argumento.</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> No se devuelve un valor al código de llamada. Si no se está ejecutando un proceso de Bloc de notas, el ejemplo genera un <xref:System.ArgumentException>.</xref:System.ArgumentException> El `Shell` procedimiento se supone que las aplicaciones están en las rutas especificadas.  
  
     [!code-vb[VbVbalrCatRef&#11;](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A></xref:Microsoft.VisualBasic.Interaction.Shell%2A>   
 <xref:System.ArgumentException></xref:System.ArgumentException>   
 [Procedimientos](./index.md)   
 [Sub (procedimientos)](./sub-procedures.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Cómo: crear un procedimiento](./how-to-create-a-procedure.md)   
 [Cómo: llamar a un procedimiento que devuelve un valor](./how-to-call-a-procedure-that-returns-a-value.md)   
 [Cómo: llamar a un controlador de eventos en Visual Basic](./how-to-call-an-event-handler.md)
