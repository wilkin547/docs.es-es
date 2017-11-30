---
title: Solucionar problemas de controladores de eventos heredados en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e0e8f0b669566bbee6530931bfba9808fad0c085
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>Solucionar problemas de controladores de eventos heredados en Visual Basic
Este tema enumeran los problemas comunes que surgen con controladores de eventos en componentes heredados.  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>Código de controlador de eventos se ejecuta dos veces por cada llamada  
  
-   Un controlador de eventos heredado no debe incluir un [controla](../../../../visual-basic/language-reference/statements/handles-clause.md) cláusula. El método de la clase base ya está asociado con el evento y se activará en consecuencia. Quitar el `Handles` cláusula del método heredado.  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]  
  
-   Si el método heredado no tiene una `Handles` (palabra clave), compruebe que el código no contiene un archivo extra [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) o métodos adicionales que controlen el mismo evento.  
  
## <a name="see-also"></a>Vea también  
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)
