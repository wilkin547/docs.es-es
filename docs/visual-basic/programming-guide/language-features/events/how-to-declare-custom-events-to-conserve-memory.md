---
title: Procedimiento Declarar eventos personalizados para conservar memoria (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: bf22c2029671588ab0ebaefd2554fcb2a5a1131c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719526"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Procedimiento Declarar eventos personalizados para conservar memoria (Visual Basic)
Hay varias circunstancias cuando es importante que una aplicación mantener el uso de memoria baja. Eventos personalizados que la aplicación utilice solo para los eventos que controla la memoria.  
  
 De forma predeterminada, cuando una clase declara un evento, el compilador asigna memoria para un campo almacenar la información del evento. Si una clase tiene muchos eventos no usados, innecesariamente a tomar la memoria.  
  
 En lugar de usar la implementación predeterminada de los eventos que proporciona Visual Basic, puede usar los eventos personalizados para administrar el uso de memoria más detenidamente.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la clase utiliza una instancia de la <xref:System.ComponentModel.EventHandlerList> (clase), almacenado en el `Events` campo para almacenar información sobre los eventos en uso. El <xref:System.ComponentModel.EventHandlerList> es una clase de lista optimizada están diseñada para contener los delegados.  
  
 Todos los eventos de la clase utilizan el `Events` campo para realizar un seguimiento de los métodos que controla cada evento.  
  
 [!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.ComponentModel.EventHandlerList>
- [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Cómo: Declarar eventos personalizados para evitar el bloqueo](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
