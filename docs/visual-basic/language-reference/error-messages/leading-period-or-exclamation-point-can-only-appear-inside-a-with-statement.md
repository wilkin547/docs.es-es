---
title: Iniciales &#39;. &#39; o &#39;! &#39; solo puede aparecer dentro de un &#39;con&#39; instrucción
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: e64318d4ececbd887f55a1a202cc2d58c90c8fc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625957"
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a>Iniciales &#39;. &#39; o &#39;! &#39; solo puede aparecer dentro de un &#39;con&#39; instrucción
Un punto (.) o signo de exclamación (!) que no está dentro un `With` bloque aparece sin una expresión de la izquierda. Acceso a miembros (`.`) y acceso a miembros de diccionario (`!`) requieren una expresión que especifica el elemento que contiene el miembro. Esto debe aparecer inmediatamente a la izquierda del descriptor de acceso o como destino de una `With` bloque que contiene el acceso a miembros.  
  
 **Identificador de error:** BC30157  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que el `With` bloque tiene el formato correcto.  
  
2.  Si no hay ningún `With` bloquear, agregue una expresión a la izquierda del descriptor de acceso que se evalúa como un elemento definido que contiene el miembro.  
  
## <a name="see-also"></a>Vea también
- [Caracteres especiales en el código](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [With...End With (instrucción)](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
