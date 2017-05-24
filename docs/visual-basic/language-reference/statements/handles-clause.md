---
title: "Handles (cláusula, Visual Basic) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- Handles
- vb.Handles
dev_langs:
- VB
helpviewer_keywords:
- Handles keyword
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7c79935e7f15f31abca7efddbc443239d5db2f58
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="handles-clause-visual-basic"></a>Handles (Cláusula, Visual Basic)
Declara que un procedimiento controla un evento especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
proceduredeclaration Handles eventlist  
```  
  
## <a name="parts"></a>Elementos  
 `proceduredeclaration`  
 La declaración de procedimiento `Sub` del procedimiento que controlará el evento.  
  
 `eventlist`  
 Lista de los eventos que `proceduredeclaration` debe controlar, separados por comas. Los eventos deben ser generados bien por la clase base de la clase actual o bien por un objeto declarado mediante la palabra clave `WithEvents`.  
  
## <a name="remarks"></a>Comentarios  
 Utilice la palabra clave `Handles` al final de una declaración de procedimiento para que controle los eventos generados por una variable de objeto declarada mediante el uso de la palabra clave `WithEvents` . La palabra clave `Handles` también puede usarse en una clase derivada para controlar eventos de una clase base.  
  
 La palabra clave `Handles` y la instrucción `AddHandler` permiten especificar que determinados procedimientos controlen eventos determinados, pero hay diferencias. Use la palabra clave `Handles` al definir un procedimiento para especificar que controla un evento determinado. La instrucción `AddHandler` conecta los procedimientos a los eventos en tiempo de ejecución. Para obtener más información, consulte [AddHandler (instrucción)](../../../visual-basic/language-reference/statements/addhandler-statement.md).  
  
 Para los eventos personalizados, la aplicación invoca al descriptor de acceso `AddHandler` del evento cuando agrega el procedimiento como un controlador de eventos. Para obtener más información sobre los eventos personalizados, vea [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrEvents&#2;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_1.vb)]  
  
 En el siguiente ejemplo se demuestra cómo una clase derivada puede usar la instrucción `Handles` para controlar un evento de una clase base.  
  
 [!code-vb[VbVbalrEvents&3;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente contiene dos controladores de eventos para un **aplicación WPF** proyecto.  
  
 [!code-vb[VbVbalrEvents nº&41;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_3.vb)]  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo es equivalente al ejemplo anterior. El `eventlist` en la cláusula `Handles` contiene los eventos de ambos botones.  
  
 [!code-vb[VbVbalrEvents&#42;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_4.vb)]  
  
## <a name="see-also"></a>Vea también  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)   
 [AddHandler (instrucción)](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [RemoveHandler (instrucción)](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)   
 [RaiseEvent (instrucción)](../../../visual-basic/language-reference/statements/raiseevent-statement.md)   
 [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)

