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
ms.openlocfilehash: 704ca667a6d14ade7be0192e872f5e40791cb864
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58830193"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>Solucionar problemas de controladores de eventos heredados en Visual Basic
En este tema se enumera problemas comunes que surgen con controladores de eventos en componentes heredados.  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>Código de controlador de eventos se ejecuta dos veces para todas las llamadas  
  
-   Un controlador de eventos heredado no debe incluir un [controla](../../../../visual-basic/language-reference/statements/handles-clause.md) cláusula. El método de la clase base ya está asociado con el evento y se activará en consecuencia. Quitar el `Handles` cláusula del método heredado.  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
-   Si el método heredado no tiene un `Handles` palabra clave, compruebe que el código no contiene un archivo extra [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) o métodos adicionales que controlan el mismo evento.  
  
## <a name="see-also"></a>Vea también

- [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)
