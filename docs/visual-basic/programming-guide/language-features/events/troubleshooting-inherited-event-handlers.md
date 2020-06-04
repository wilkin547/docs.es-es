---
title: Solución de problemas de controladores de eventos heredados
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: 4e7bedd1de5197fcf8b69091f4cc878f41b01cd5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405111"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>Solucionar problemas de controladores de eventos heredados en Visual Basic
En este tema se enumeran los problemas comunes que surgen con los controladores de eventos en componentes heredados.  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>El código del controlador de eventos se ejecuta dos veces para cada llamada  
  
- Un controlador de eventos heredado no debe incluir una cláusula [Handles](../../../language-reference/statements/handles-clause.md) . El método de la clase base ya está asociado al evento y se activará en consecuencia. Quite la `Handles` cláusula del método heredado.  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
- Si el método heredado no tiene una `Handles` palabra clave, compruebe que el código no contiene una [instrucción AddHandler](../../../language-reference/statements/addhandler-statement.md) adicional o cualquier otro método que controle el mismo evento.  
  
## <a name="see-also"></a>Vea también

- [Eventos](index.md)
