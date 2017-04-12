---
title: "Cómo: declarar eventos personalizados para conservar memoria (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: 11
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
ms.openlocfilehash: 4f8ce32a3b4da411a73010119283ce9661b82a6c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Cómo: Declarar eventos personalizados para conservar memoria (Visual Basic)
Hay varias circunstancias, es importante que una aplicación conserve su uso de memoria baja. Los eventos personalizados permiten utilizar memoria sólo para los eventos que controla la aplicación.  
  
 De forma predeterminada, cuando una clase declara un evento, el compilador asigna memoria para un campo almacenar la información de evento. Si una clase tiene muchos eventos no usados, innecesariamente ocupan memoria.  
  
 En lugar de usar la implementación predeterminada de eventos que proporciona Visual Basic, puede utilizar eventos personalizados para administrar el uso de memoria más detenidamente.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la clase utiliza una instancia de la <xref:System.ComponentModel.EventHandlerList>(clase), almacenado en los `Events` campo para almacenar información sobre los eventos en uso.</xref:System.ComponentModel.EventHandlerList> El <xref:System.ComponentModel.EventHandlerList>es una clase de lista optimizada diseñada para contener delegados.</xref:System.ComponentModel.EventHandlerList>  
  
 Todos los eventos de la clase usan el `Events` campo para realizar un seguimiento de qué métodos está controlando cada evento.  
  
 [!code-vb[VbVbalrEvents&#22;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ComponentModel.EventHandlerList></xref:System.ComponentModel.EventHandlerList>   
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)   
 [Declarar eventos personalizados para evitar bloqueos](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
