---
title: Procedimiento para declarar eventos personalizados para conservar memoria
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: 78934e3e5ae7d5a3f5867c99a9f1db760c65ecbf
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075127"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Cómo: Declarar eventos personalizados para conservar memoria (Visual Basic)

Hay varias circunstancias en las que es importante que una aplicación mantenga bajo el uso de memoria. Los eventos personalizados permiten que la aplicación use la memoria solo para los eventos que controla.  
  
 De forma predeterminada, cuando una clase declara un evento, el compilador asigna memoria para un campo que almacena la información del evento. Si una clase tiene muchos eventos sin usar, ocupan memoria innecesariamente.  
  
 En lugar de usar la implementación predeterminada de eventos que proporciona Visual Basic, puede usar eventos personalizados para administrar el uso de memoria con más detenimiento.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo, la clase utiliza una instancia de la <xref:System.ComponentModel.EventHandlerList> clase, almacenada en el `Events` campo, para almacenar información sobre los eventos en uso. La <xref:System.ComponentModel.EventHandlerList> clase es una clase de lista optimizada diseñada para contener delegados.  
  
 Todos los eventos de la clase usan el `Events` campo para realizar un seguimiento de los métodos que controlan cada evento.  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.ComponentModel.EventHandlerList>
- [Eventos](index.md)
- [Procedimiento para declarar eventos personalizados para evitar bloqueos](how-to-declare-custom-events-to-avoid-blocking.md)
