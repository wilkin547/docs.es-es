---
title: 'Cómo: Declarar eventos personalizados para conservar memoria'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: 3cc2d3ea57f1a8daf704c2c929baf3f2acf78c17
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345129"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Cómo: Declarar eventos personalizados para conservar memoria (Visual Basic)
Hay varias circunstancias en las que es importante que una aplicación mantenga bajo el uso de memoria. Los eventos personalizados permiten que la aplicación use la memoria solo para los eventos que controla.  
  
 De forma predeterminada, cuando una clase declara un evento, el compilador asigna memoria para un campo que almacena la información del evento. Si una clase tiene muchos eventos sin usar, ocupan memoria innecesariamente.  
  
 En lugar de usar la implementación predeterminada de eventos que proporciona Visual Basic, puede usar eventos personalizados para administrar el uso de memoria con más detenimiento.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la clase utiliza una instancia de la clase <xref:System.ComponentModel.EventHandlerList>, almacenada en el campo `Events`, para almacenar información sobre los eventos en uso. La clase <xref:System.ComponentModel.EventHandlerList> es una clase de lista optimizada diseñada para contener delegados.  
  
 Todos los eventos de la clase usan el campo `Events` para realizar un seguimiento de los métodos que controlan cada evento.  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.ComponentModel.EventHandlerList>
- [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Declarar eventos personalizados para evitar bloqueos](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
