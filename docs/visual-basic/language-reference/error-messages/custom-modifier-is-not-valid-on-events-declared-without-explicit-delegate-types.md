---
title: "El modificador &#39;Custom&#39; no es v&#225;lido en eventos declarados sin tipos de delegado expl&#237;citos | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc31122"
  - "bc31122"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31122"
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# El modificador &#39;Custom&#39; no es v&#225;lido en eventos declarados sin tipos de delegado expl&#237;citos
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

A diferencia de un evento no personalizado, una declaración `Custom Event` requiere una cláusula `As` que sigue al nombre de evento que especifica explícitamente el tipo de delegado para el evento.  
  
 Los eventos no personalizados se pueden definir con una cláusula `As` y un tipo de delegado explícito, o bien, con una lista de parámetros especificada a continuación del nombre del evento.  
  
 **Identificador de error:** BC31122  
  
### Para corregir este error  
  
1.  Defina un delegado con la misma lista de parámetros que la del evento personalizado.  
  
     Por ejemplo, si `Custom Event Test(ByVal sender As Object, ByVal i As Integer)` definiera `Custom Event`, el delegado correspondiente sería el siguiente.  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  Reemplace la lista de parámetros del evento personalizado con una cláusula `As` que especifica el tipo de delegado.  
  
     Continuando con el ejemplo, la declaración `Custom Event` se volvería a escribir como sigue.  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## Ejemplo  
 Este ejemplo declara un `Custom Event` y especifica la cláusula `As` necesaria con un tipo de delegado.  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## Vea también  
 [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Delegate \(Instrucción\)](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Eventos](../../../visual-basic/programming-guide/language-features/events/events.md)