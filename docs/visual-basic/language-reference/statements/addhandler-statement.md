---
description: 'Más información sobre: AddHandler (instrucción)'
title: AddHandler (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: c0c34abd7ff225765ab36278825a555e2b84b0d1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674108"
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
  
## <a name="see-also"></a>Vea también

- [RemoveHandler (Instrucción)](removehandler-statement.md)
- [Asas](handles-clause.md)
- [Event (Instrucción)](event-statement.md)
- [Eventos](../../programming-guide/language-features/events/index.md)
