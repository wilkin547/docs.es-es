---
title: Filtrar Declarar eventos personalizados para evitar bloqueos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 6eea47ea2c8aee697eb34ca904dad22ca88e6ce4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821262"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Filtrar Declarar eventos personalizados para evitar bloqueos (Visual Basic)
Hay varias circunstancias cuando es importante que un controlador de eventos no bloquear los controladores de eventos posteriores. Eventos personalizados permiten el evento llame a sus controladores de eventos de forma asincrónica.  
  
 De forma predeterminada, el campo de almacén de respaldo para una declaración de evento es un delegado de multidifusión que combina todos los controladores de eventos de forma consecutiva. Esto significa que si un controlador tarda mucho tiempo en completarse, bloquea los otros controladores hasta que se complete. (Los controladores de eventos exhiben nunca deben realizar las operaciones largas o puede producir bloqueos.)  
  
 En lugar de usar la implementación predeterminada de los eventos que proporciona Visual Basic, puede usar un evento personalizado para ejecutar los controladores de eventos de forma asincrónica.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, el `AddHandler` descriptor de acceso agrega el delegado para cada controlador de la `Click` eventos a un <xref:System.Collections.ArrayList> almacenados en el `EventHandlerList` campo.  
  
 Cuando el código genera el `Click` eventos, el `RaiseEvent` descriptor de acceso invoca todos los delegados de controlador de eventos utilizando de forma asincrónica el <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> método. Ese método invoca cada controlador en un subproceso de trabajo y se devuelve inmediatamente, por lo que los controladores no bloqueen entre sí.  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Cómo: Declarar eventos personalizados para conservar memoria](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
