---
title: "'.' o '!' inicial sólo puede aparecer dentro de una instrucción 'With'"
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 4ff273d5930fe58a5bccf0f4f4c10e971d777d01
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162510"
---
# <a name="bc30157-leading--or--can-only-appear-inside-a-with-statement"></a>BC30157: '. ' o '! ' inicial solo puede aparecer dentro de una instrucción ' with '

Un punto (.) o un signo de exclamación (!) que no está dentro de un `With` bloque se produce sin una expresión a la izquierda. El acceso a miembros ( `.` ) y el acceso a miembros de diccionario ( `!` ) requieren una expresión que especifique el elemento que contiene el miembro. Debe aparecer inmediatamente a la izquierda del descriptor de acceso o como destino de un `With` bloque que contiene el acceso a miembros.

 **Identificador de error:** BC30157

## <a name="to-correct-this-error"></a>Para corregir este error

1. Asegúrese de que el `With` bloque tenga el formato correcto.

2. Si no hay ningún `With` bloque, agregue una expresión a la izquierda del descriptor de acceso que se evalúe como un elemento definido que contiene el miembro.

## <a name="see-also"></a>Vea también

- [Caracteres especiales en el código](../../programming-guide/program-structure/special-characters-in-code.md)
- [Instrucción With...End With](../statements/with-end-with-statement.md)
