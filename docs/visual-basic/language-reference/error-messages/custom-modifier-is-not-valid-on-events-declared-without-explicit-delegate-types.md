---
description: "Más información sobre: BC31122: el modificador ' Custom ' no es válido en eventos declarados sin tipos de delegado explícitos"
title: El modificador 'Custom' no es válido en eventos declarados sin tipos de delegado explícitos
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 6cbddd31dfa9c923038f8ea706bfc49233574cfb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796683"
---
# <a name="bc31122-custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>BC31122: el modificador ' Custom ' no es válido en eventos declarados sin tipos de delegado explícitos

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

## <a name="see-also"></a>Vea también

- [Event (Instrucción)](../statements/event-statement.md)
- [Delegate (Instrucción)](../statements/delegate-statement.md)
- [Eventos](../../programming-guide/language-features/events/index.md)
