---
title: '&#39;Personalizado&#39; modificador no es válido en eventos declarados sin tipos de delegado explícitos'
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 3f08bbbbbac4a01dfbac8d15cf9285c01262618a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>&#39;Personalizado&#39; modificador no es válido en eventos declarados sin tipos de delegado explícitos
A diferencia de un evento no personalizado, un `Custom Event` declaración requiere un `As` cláusula después el nombre del evento que especifica explícitamente el tipo de delegado para el evento.  
  
 Eventos personalizados no se pueden definir con un `As` cláusula y explícito tipo de delegado, o con un parámetro de lista inmediatamente después del nombre de evento.  
  
 **Id. de error:** BC31122  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Defina a un delegado con la misma lista de parámetros que el evento personalizado.  
  
     Por ejemplo, si la `Custom Event` definieron de forma `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, a continuación, el delegado correspondiente sería la siguiente.  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  Reemplazar la lista de parámetros del evento personalizado con un `As` cláusula que especifica el tipo de delegado.  
  
     Siguiendo con el ejemplo, `Custom Event` sería reescrita declaración como se indica a continuación.  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se declara un `Custom Event` y especifica los necesarios `As` cláusula con un tipo de delegado.  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)
