---
title: 'Cómo: Declarar eventos personalizados para evitar bloqueos'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 8d73d9c4590afb33e7176f647069cafcb3a9d7d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345145"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Cómo: Declarar eventos personalizados para evitar bloqueos (Visual Basic)
Hay varias circunstancias en las que es importante que un controlador de eventos no bloquee los controladores de eventos subsiguientes. Los eventos personalizados permiten que el evento llame a sus controladores de eventos de forma asincrónica.  
  
 De forma predeterminada, el campo de almacenamiento de copia de seguridad de una declaración de evento es un delegado de multidifusión que combina en serie todos los controladores de eventos. Esto significa que si un controlador tarda mucho tiempo en completarse, bloquea los demás controladores hasta que se completa. (Los controladores de eventos bien comprobables nunca deben realizar operaciones largas o de bloqueo).  
  
 En lugar de usar la implementación predeterminada de eventos que proporciona Visual Basic, puede usar un evento personalizado para ejecutar los controladores de eventos de forma asincrónica.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, el descriptor de acceso `AddHandler` agrega el delegado de cada controlador del evento `Click` a un <xref:System.Collections.ArrayList> almacenado en el campo `EventHandlerList`.  
  
 Cuando el código genera el evento `Click`, el descriptor de acceso `RaiseEvent` invoca de forma asincrónica todos los delegados de controlador de eventos utilizando el método <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>. Ese método invoca cada controlador en un subproceso de trabajo y vuelve inmediatamente, por lo que los controladores no pueden bloquearse entre sí.  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Declarar eventos personalizados para conservar memoria](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
