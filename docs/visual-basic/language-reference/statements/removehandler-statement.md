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
ms.openlocfilehash: a815241f20be12b3b7b4f2b87d50a8965021bbf0
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871943"
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
  
## <a name="remarks"></a>Comentarios  

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
