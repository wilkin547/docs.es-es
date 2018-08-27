---
title: RemoveHandler (instrucción) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: c1e6ffec64bc01936955a2e94aa9c110b317109f
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925171"
---
# <a name="removehandler-statement"></a>RemoveHandler (Instrucción)
Quita la asociación entre un evento y un controlador de eventos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|de esquema JSON|  
|---|---|  
|`event`|El nombre del evento que se está controlando.|  
|`eventhandler`|El nombre del procedimiento que actualmente controla el evento.|  
  
## <a name="remarks"></a>Comentarios  
 El `AddHandler` y `RemoveHandler` instrucciones le permiten iniciar y detener el control de eventos para un evento concreto en cualquier momento durante la ejecución del programa.  
  
> [!NOTE]
>  Para los eventos personalizados, el `RemoveHandler` instrucción invoca el evento `RemoveHandler` descriptor de acceso. Para obtener más información sobre los eventos personalizados, vea [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [AddHandler (instrucción)](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)
