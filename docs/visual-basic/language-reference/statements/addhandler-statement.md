---
title: AddHandler (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: c110116af75d4fb39c016b8d6afcdb707fa6599b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350188"
---
# <a name="addhandler-statement"></a>AddHandler (Instrucción)
Asocia un evento a un controlador de eventos en tiempo de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Elementos  
|||
|---|---|
|event|Nombre del evento que se va a controlar.|  
|`eventhandler`|Nombre de un procedimiento que controla el evento.|
|||
  
## <a name="remarks"></a>Comentarios  
 Las instrucciones `AddHandler` y `RemoveHandler` permiten iniciar y detener el control de eventos en cualquier momento durante la ejecución del programa.  
  
 La firma del procedimiento `eventhandler` debe coincidir con la firma del `event`de eventos.  
  
 La palabra clave `Handles` y la instrucción `AddHandler` permiten especificar que determinados procedimientos controlen eventos determinados, pero hay diferencias. La instrucción `AddHandler` conecta los procedimientos a los eventos en tiempo de ejecución. Use la palabra clave `Handles` al definir un procedimiento para especificar que controla un evento determinado. Para obtener más información, vea [identificadores](../../../visual-basic/language-reference/statements/handles-clause.md).  
  
> [!NOTE]
> En el caso de los eventos personalizados, la instrucción `AddHandler` invoca al descriptor de acceso `AddHandler` del evento. Para obtener más información sobre los eventos personalizados, vea [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Vea también

- [RemoveHandler (instrucción)](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)
- [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)
