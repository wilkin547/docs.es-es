---
title: El modificador 'Custom' no es válido en eventos declarados sin tipos de delegado explícitos
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: c1b57ccdaa9e04c837ecf7572bc164683a934b2d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273522"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>El modificador 'Custom' no es válido en eventos declarados sin tipos de delegado explícitos
A diferencia de un evento no personalizado, un `Custom Event` declaración requiere un `As` cláusula después del nombre de evento que se especifica explícitamente el tipo de delegado para el evento.  
  
 Los eventos no personalizados pueden ser definido con un `As` cláusula y explícita el tipo delegado, o con un parámetro de lista inmediatamente después del nombre de evento.  
  
 **Identificador de error:** BC31122  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Defina a un delegado con la misma lista de parámetros como el evento personalizado.  
  
     Por ejemplo, si la `Custom Event` se ha definido por `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, a continuación, el delegado correspondiente sería la siguiente.  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  Reemplazar la lista de parámetros del evento personalizado con un `As` cláusula que especifica el tipo de delegado.  
  
     Continuando con el ejemplo, `Custom Event` declaración se volvería como sigue.  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se declara un `Custom Event` y especifica los `As` cláusula con un tipo de delegado.  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a>Vea también
- [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)
- [Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)
