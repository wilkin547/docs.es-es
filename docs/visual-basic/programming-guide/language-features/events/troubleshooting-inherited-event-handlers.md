---
title: Solucionar problemas de controladores de eventos heredados en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: e7c56757d18a22a65b4ef8e81d2a05e5f4f4dffc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680210"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>Solucionar problemas de controladores de eventos heredados en Visual Basic
En este tema se enumera problemas comunes que surgen con controladores de eventos en componentes heredados.  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>Código de controlador de eventos se ejecuta dos veces para todas las llamadas  
  
-   Un controlador de eventos heredado no debe incluir un [controla](../../../../visual-basic/language-reference/statements/handles-clause.md) cláusula. El método de la clase base ya está asociado con el evento y se activará en consecuencia. Quitar el `Handles` cláusula del método heredado.  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]  
  
-   Si el método heredado no tiene un `Handles` palabra clave, compruebe que el código no contiene un archivo extra [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) o métodos adicionales que controlan el mismo evento.  
  
## <a name="see-also"></a>Vea también
- [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)
