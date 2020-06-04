---
title: El modificador 'Custom' no es válido en eventos declarados sin tipos de delegado explícitos
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 0c5a4188fedf9685afdd1cde4c1de93a0b43b919
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409793"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>El modificador 'Custom' no es válido en eventos declarados sin tipos de delegado explícitos
A diferencia de un evento no personalizado, una `Custom Event` declaración requiere una `As` cláusula que siga el nombre del evento que especifica explícitamente el tipo de delegado para el evento.  
  
 Los eventos no personalizados se pueden definir con una `As` cláusula y un tipo de delegado explícito, o con una lista de parámetros inmediatamente después del nombre del evento.  
  
 **Identificador de error:** BC31122  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Defina un delegado con la misma lista de parámetros que el evento personalizado.  
  
     Por ejemplo, si `Custom Event` se definió mediante `Custom Event Test(ByVal sender As Object, ByVal i As Integer)` , el delegado correspondiente sería el siguiente.  
  
     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]  
  
2. Reemplace la lista de parámetros del evento personalizado por una `As` cláusula que especifique el tipo de delegado.  
  
     Siguiendo con el ejemplo, la `Custom Event` declaración se volvería a escribir de la siguiente manera.  
  
     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo declara `Custom Event` y especifica la `As` cláusula necesaria con un tipo de delegado.  
  
 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]  
  
## <a name="see-also"></a>Consulte también

- [Event (Instrucción)](../statements/event-statement.md)
- [Delegate (Instrucción)](../statements/delegate-statement.md)
- [Eventos](../../programming-guide/language-features/events/index.md)
