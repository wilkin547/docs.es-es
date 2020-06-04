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
ms.openlocfilehash: 3514a79f2430b148e6a3727b83029b4e207a677b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404257"
---
# <a name="removehandler-statement"></a>RemoveHandler (Instrucción)
Quita la asociación entre un evento y un controlador de eventos.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`event`|Nombre del evento que se está controlando.|  
|`eventhandler`|Nombre del procedimiento que está controlando el evento.|  
  
## <a name="remarks"></a>Observaciones  
 Las `AddHandler` `RemoveHandler` instrucciones y permiten iniciar y detener el control de eventos para un evento concreto en cualquier momento durante la ejecución del programa.  
  
> [!NOTE]
> En el caso de los eventos personalizados, la `RemoveHandler` instrucción invoca al `RemoveHandler` descriptor de acceso del evento. Para obtener más información sobre los eventos personalizados, vea [Event Statement](event-statement.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Consulte también

- [AddHandler (Instrucción)](addhandler-statement.md)
- [Asas](handles-clause.md)
- [Event (Instrucción)](event-statement.md)
- [Eventos](../../programming-guide/language-features/events/index.md)
