---
title: El operando 'AddressOf' debe ser el nombre de un método (sin paréntesis)
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: b8c67c2390df91c6a4af66e020365544e6bf369b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61751636"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a>El operando 'AddressOf' debe ser el nombre de un método (sin paréntesis)
El operador `AddressOf` crea una instancia de delegado de procedimiento que hace referencia a un procedimiento específico. La sintaxis es como sigue.  
  
 `AddressOf` `procedurename`  
  
 Insertar paréntesis que rodean el siguiente argumento `AddressOf`, donde no son necesarias.  
  
 **Identificador de error:** BC30577  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Quite los paréntesis que rodean el siguiente argumento `AddressOf`.  
  
2. Asegúrese de que el argumento es un nombre de método.  
  
## <a name="see-also"></a>Vea también

- [AddressOf (operador)](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md)
