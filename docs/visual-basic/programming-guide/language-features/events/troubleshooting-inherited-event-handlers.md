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
ms.openlocfilehash: f6355cf7fc2e43651c1112d048220a8179968c76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646338"
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
