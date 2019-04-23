---
title: "'.' o '!' inicial sólo puede aparecer dentro de una instrucción 'With'"
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 15390fb506fe9bca10f6917f5b26451a5569bece
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322854"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a>'.' o '!' inicial sólo puede aparecer dentro de una instrucción 'With'
Un punto (.) o signo de exclamación (!) que no está dentro un `With` bloque aparece sin una expresión de la izquierda. Acceso a miembros (`.`) y acceso a miembros de diccionario (`!`) requieren una expresión que especifica el elemento que contiene el miembro. Esto debe aparecer inmediatamente a la izquierda del descriptor de acceso o como destino de una `With` bloque que contiene el acceso a miembros.  
  
 **Identificador de error:** BC30157  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Asegúrese de que el `With` bloque tiene el formato correcto.  
  
2. Si no hay ningún `With` bloquear, agregue una expresión a la izquierda del descriptor de acceso que se evalúa como un elemento definido que contiene el miembro.  
  
## <a name="see-also"></a>Vea también

- [Caracteres especiales en el código](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [With...End With (instrucción)](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
