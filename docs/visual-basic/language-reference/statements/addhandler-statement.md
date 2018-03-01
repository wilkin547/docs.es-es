---
title: "AddHandler (Instrucción)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07fbfe04ccd01b7d0f99338ef2682238830099dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="addhandler-statement"></a>AddHandler (Instrucción)
Asocia un evento a un controlador de eventos en tiempo de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Elementos  
 `event`  
 El nombre del evento que se va a controlar.  
  
 `eventhandler`  
 El nombre de un procedimiento que controla el evento.  
  
## <a name="remarks"></a>Comentarios  
 El `AddHandler` y `RemoveHandler` instrucciones permiten iniciar y detener el control de eventos en cualquier momento durante la ejecución del programa.  
  
 La firma de la `eventhandler` procedimiento debe coincidir con la firma del evento `event`.  
  
 La palabra clave `Handles` y la instrucción `AddHandler` permiten especificar que determinados procedimientos controlen eventos determinados, pero hay diferencias. La instrucción `AddHandler` conecta los procedimientos a los eventos en tiempo de ejecución. Use la palabra clave `Handles` al definir un procedimiento para especificar que controla un evento determinado. Para obtener más información, consulte [controla](../../../visual-basic/language-reference/statements/handles-clause.md).  
  
> [!NOTE]
>  Para los eventos personalizados, la `AddHandler` instrucción invoca el evento `AddHandler` descriptor de acceso. Para obtener más información sobre eventos personalizados, vea [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [RemoveHandler (instrucción)](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)
