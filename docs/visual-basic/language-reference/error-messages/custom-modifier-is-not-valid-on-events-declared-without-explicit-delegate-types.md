---
title: "El modificador &quot;Custom&quot; no es válido en eventos declarados sin tipos de delegado explícitos | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31122
- bc31122
dev_langs:
- VB
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: 9
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 0e70fca6a0608df5db43156f70196b4e5c9b2339
ms.lasthandoff: 03/13/2017

---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>El modificador 'Custom' no es válido en eventos declarados sin tipos de delegado explícitos
A diferencia de un evento no personalizado, un `Custom Event` declaración requiere un `As` cláusula después el nombre del evento que especifica explícitamente el tipo de delegado para el evento.  
  
 Eventos personalizados no se puede definir mediante una `As` cláusula y explícita tipo delegado o con un parámetro de lista inmediatamente después del nombre del evento.  
  
 **Id. de error:** BC31122  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Defina a un delegado con la misma lista de parámetros que el evento personalizado.  
  
     Por ejemplo, si la `Custom Event` definido por `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, a continuación, el delegado correspondiente sería el siguiente.  
  
     [!code-vb[VbVbalrEventError&#18;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  Reemplazar la lista de parámetros del evento personalizado con un `As` cláusula que especifica el tipo de delegado.  
  
     Continuando con el ejemplo `Custom Event` se volvería declaración como sigue.  
  
     [!code-vb[VbVbalrEventError Nº&19;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo declara un `Custom Event` y especifica el necesaria `As` cláusula con un tipo de delegado.  
  
 [!code-vb[VbVbalrEventError&#2;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)
