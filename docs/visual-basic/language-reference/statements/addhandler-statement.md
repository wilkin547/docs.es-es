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
ms.openlocfilehash: de995a13b34678410e2af74b59f2d0c467982b75
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408489"
---
# <a name="addhandler-statement"></a>AddHandler (Instrucción)
Asocia un evento a un controlador de eventos en tiempo de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Partes  
|||
|---|---|
|event|Nombre del evento que se va a controlar.|  
|`eventhandler`|Nombre de un procedimiento que controla el evento.|
|||
  
## <a name="remarks"></a>Observaciones  
 Las `AddHandler` `RemoveHandler` instrucciones y permiten iniciar y detener el control de eventos en cualquier momento durante la ejecución del programa.  
  
 La firma del `eventhandler` procedimiento debe coincidir con la firma del evento `event` .  
  
 La palabra clave `Handles` y la instrucción `AddHandler` permiten especificar que determinados procedimientos controlen eventos determinados, pero hay diferencias. La instrucción `AddHandler` conecta los procedimientos a los eventos en tiempo de ejecución. Use la palabra clave `Handles` al definir un procedimiento para especificar que controla un evento determinado. Para obtener más información, vea [identificadores](handles-clause.md).  
  
> [!NOTE]
> En el caso de los eventos personalizados, la `AddHandler` instrucción invoca al `AddHandler` descriptor de acceso del evento. Para obtener más información sobre los eventos personalizados, vea [Event Statement](event-statement.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Consulte también

- [RemoveHandler (Instrucción)](removehandler-statement.md)
- [Asas](handles-clause.md)
- [Event (Instrucción)](event-statement.md)
- [Eventos](../../programming-guide/language-features/events/index.md)
