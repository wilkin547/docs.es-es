---
title: RemoveHandler (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 177952acf362ccb36a36b5f09b11a1a93dbefa29
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333035"
---
# <a name="removehandler-statement"></a>RemoveHandler (Instrucción)
Quita la asociación entre un evento y un controlador de eventos.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`event`|Nombre del evento que se está controlando.|  
|`eventhandler`|Nombre del procedimiento que está controlando el evento.|  
  
## <a name="remarks"></a>Comentarios  
 Las instrucciones `AddHandler` y `RemoveHandler` permiten iniciar y detener el control de eventos para un evento concreto en cualquier momento durante la ejecución del programa.  
  
> [!NOTE]
> En el caso de los eventos personalizados, la instrucción `RemoveHandler` invoca al descriptor de acceso `RemoveHandler` del evento. Para obtener más información sobre los eventos personalizados, vea [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Vea también

- [AddHandler (instrucción)](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)
- [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)
