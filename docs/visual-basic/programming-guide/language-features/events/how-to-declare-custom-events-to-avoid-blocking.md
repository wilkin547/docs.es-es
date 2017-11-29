---
title: "Cómo: Declarar eventos personalizados para evitar bloqueos (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a36c855efb67752674615a61f2fa701974ce5f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Cómo: Declarar eventos personalizados para evitar bloqueos (Visual Basic)
Hay varias circunstancias cuando es importante que un controlador de eventos no se bloqueará siguientes controladores de eventos. Los eventos personalizados permiten el evento llamar a sus controladores de eventos de forma asincrónica.  
  
 De forma predeterminada, el campo de almacén de respaldo de una declaración de evento es un delegado multidifusión que combina de forma consecutiva todos los controladores de eventos. Esto significa que si un controlador tarda mucho tiempo en completarse, bloquea los demás controladores hasta que se complete. (Controladores de eventos con buen comportamiento nunca deben realizar las operaciones largas o puede producir bloqueos.)  
  
 En lugar de usar la implementación predeterminada de eventos que proporciona Visual Basic, puede usar un evento personalizado para ejecutar los controladores de eventos de forma asincrónica.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, el `AddHandler` descriptor de acceso agrega el delegado para cada controlador de la `Click` eventos a una <xref:System.Collections.ArrayList> almacenados en los `EventHandlerList` campo.  
  
 Cuando el código genera el `Click` eventos, el `RaiseEvent` descriptor de acceso invoca todos los delegados de controlador de eventos asincrónicamente mediante el <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> método. Ese método invoca cada controlador en un subproceso de trabajo y devuelve inmediatamente, por lo que no pueden bloquear controladores entre sí.  
  
 [!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.ArrayList>  
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>  
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Declarar eventos personalizados para conservar memoria](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
