---
title: Instrucción AddHandler (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: 95277f532488b0cf56114e5ee94dc3528e3a2e02
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004546"
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
|evento|Nombre del evento que se va a controlar.|  
|`eventhandler`|Nombre de un procedimiento que controla el evento.|
|||
  
## <a name="remarks"></a>Comentarios  
 Las instrucciones `AddHandler` y `RemoveHandler` permiten iniciar y detener el control de eventos en cualquier momento durante la ejecución del programa.  
  
 La firma del procedimiento `eventhandler` debe coincidir con la firma del evento `event`.  
  
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
