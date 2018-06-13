---
title: A la izquierda &#39;. &#39; o &#39;! &#39; solo puede aparecer dentro de un &#39;con&#39; instrucción
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 7802b8e0aaf3dff83d5bfbe11f0b8bb1b5bb46cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589452"
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a>A la izquierda &#39;. &#39; o &#39;! &#39; solo puede aparecer dentro de un &#39;con&#39; instrucción
Un punto (.) o un signo de exclamación (!) que no está dentro un `With` bloqueo se produce sin una expresión de la izquierda. Acceso a miembros (`.`) y acceso a miembros de diccionario (`!`) requieren una expresión que especifica el elemento que contiene el miembro. Esto debe aparecer inmediatamente a la izquierda del descriptor de acceso o como destino de una `With` bloque que contiene el acceso a miembros.  
  
 **Id. de error:** BC30157  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que el `With` bloque tiene el formato correcto.  
  
2.  Si no hay ningún `With` bloquear, agregue una expresión a la izquierda del descriptor de acceso que se evalúa como un elemento definido que contiene el miembro.  
  
## <a name="see-also"></a>Vea también  
 [Caracteres especiales en el código](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 [With...End With (instrucción)](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
