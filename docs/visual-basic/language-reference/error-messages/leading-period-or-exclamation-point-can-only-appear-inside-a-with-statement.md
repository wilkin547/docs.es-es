---
title: "'.' o '!' inicial sólo puede aparecer dentro de una instrucción 'With'"
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 4821dbab90eec3c99c0996e8bff10d51b5a8f99d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824954"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a>'.' o '!' inicial sólo puede aparecer dentro de una instrucción 'With'
Un punto (.) o signo de exclamación (!) que no está dentro un `With` bloque aparece sin una expresión de la izquierda. Acceso a miembros (`.`) y acceso a miembros de diccionario (`!`) requieren una expresión que especifica el elemento que contiene el miembro. Esto debe aparecer inmediatamente a la izquierda del descriptor de acceso o como destino de una `With` bloque que contiene el acceso a miembros.  
  
 **Identificador de error:** BC30157  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que el `With` bloque tiene el formato correcto.  
  
2.  Si no hay ningún `With` bloquear, agregue una expresión a la izquierda del descriptor de acceso que se evalúa como un elemento definido que contiene el miembro.  
  
## <a name="see-also"></a>Vea también

- [Caracteres especiales en el código](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [With...End With (instrucción)](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
