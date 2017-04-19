---
title: "Cómo: declarar eventos personalizados para evitar bloqueos (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declaring events, custom
- events [Visual Basic], custom
- custom events
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
caps.latest.revision: 12
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 34b222bdbfdae0673b7150c220ca477b7e286dda
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Cómo: Declarar eventos personalizados para evitar bloqueos (Visual Basic)
Hay varias circunstancias cuando es importante que un controlador de eventos no bloquea los controladores de eventos subsiguientes. Los eventos personalizados permiten el evento llamar a sus controladores de eventos de forma asincrónica.  
  
 De forma predeterminada, el campo de almacén de respaldo de una declaración de evento es un delegado multidifusión que combina de forma consecutiva todos los controladores de eventos. Esto significa que si un controlador tarda mucho tiempo en completarse, bloquea los demás controladores hasta que se complete. (Los controladores de eventos con buen comportamiento nunca deben realizar operaciones largas o puede producir bloqueos.)  
  
 En lugar de usar la implementación predeterminada de eventos que proporciona Visual Basic, puede utilizar un evento personalizado para ejecutar los controladores de eventos de forma asincrónica.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, el `AddHandler` descriptor de acceso agrega el delegado para cada controlador de la `Click` eventos a un <xref:System.Collections.ArrayList>almacenado en el `EventHandlerList` campo.</xref:System.Collections.ArrayList>  
  
 Cuando el código provoca la `Click` evento, el `RaiseEvent` invoca el descriptor de acceso de todos los delegados de controlador de eventos utilizando de forma asincrónica el <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>(método).</xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> Ese método invoca cada controlador en un subproceso de trabajo y vuelve inmediatamente, por lo que los controladores no bloqueen entre sí.  
  
 [!code-vb[VbVbalrEvents Nº&27;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.ArrayList></xref:System.Collections.ArrayList>   
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>   
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)   
 [Declarar eventos personalizados para conservar memoria](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
