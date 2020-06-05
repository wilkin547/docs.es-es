---
title: Cláusula Handles
ms.date: 07/20/2015
f1_keywords:
- Handles
- vb.Handles
helpviewer_keywords:
- Handles keyword [Visual Basic]
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
ms.openlocfilehash: df786e4b0f0ab3795592ea57f7af17695b086cfa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404581"
---
# <a name="handles-clause-visual-basic"></a>Handles (Cláusula, Visual Basic)
Declara que un procedimiento controla un evento especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
proceduredeclaration Handles eventlist  
```  
  
## <a name="parts"></a>Partes  
 `proceduredeclaration`  
 La declaración de procedimiento `Sub` del procedimiento que controlará el evento.  
  
 `eventlist`  
 Lista de los eventos que `proceduredeclaration` debe controlar, separados por comas. Los eventos deben ser generados bien por la clase base de la clase actual o bien por un objeto declarado mediante la palabra clave `WithEvents`.  
  
## <a name="remarks"></a>Observaciones  
 Utilice la palabra clave `Handles` al final de una declaración de procedimiento para que controle los eventos generados por una variable de objeto declarada mediante el uso de la palabra clave `WithEvents` . La palabra clave `Handles` también puede usarse en una clase derivada para controlar eventos de una clase base.  
  
 La palabra clave `Handles` y la instrucción `AddHandler` permiten especificar que determinados procedimientos controlen eventos determinados, pero hay diferencias. Use la palabra clave `Handles` al definir un procedimiento para especificar que controla un evento determinado. La instrucción `AddHandler` conecta los procedimientos a los eventos en tiempo de ejecución. Para obtener más información, vea [AddHandler Statement](addhandler-statement.md).  
  
 Para los eventos personalizados, la aplicación invoca al descriptor de acceso `AddHandler` del evento cuando agrega el procedimiento como un controlador de eventos. Para obtener más información sobre los eventos personalizados, vea [Event Statement](event-statement.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#2)]  
  
 En el siguiente ejemplo se demuestra cómo una clase derivada puede usar la instrucción `Handles` para controlar un evento de una clase base.  
  
 [!code-vb[VbVbalrEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#3)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente contiene dos controladores de eventos de botón para un proyecto de **aplicación de WPF** .  
  
 [!code-vb[VbVbalrEvents#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/class3.vb#41)]  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo es equivalente al ejemplo anterior. El `eventlist` en la cláusula `Handles` contiene los eventos de ambos botones.  
  
 [!code-vb[VbVbalrEvents#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/class3.vb#42)]  
  
## <a name="see-also"></a>Consulte también

- [WithEvents](../modifiers/withevents.md)
- [AddHandler (Instrucción)](addhandler-statement.md)
- [RemoveHandler (Instrucción)](removehandler-statement.md)
- [Event (Instrucción)](event-statement.md)
- [RaiseEvent (Instrucción)](raiseevent-statement.md)
- [Eventos](../../programming-guide/language-features/events/index.md)
