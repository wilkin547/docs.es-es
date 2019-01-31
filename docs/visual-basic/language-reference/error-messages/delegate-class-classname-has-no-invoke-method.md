---
title: La clase delegada '<classname>' no tiene ningún método Invoke y, por tanto, una expresión de este tipo no puede ser el destino de una llamada a método
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 8339d038f845b8568f31f3068a98ccccf580aeae
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286655"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>Clase delegada\<classname >' no tiene ningún método Invoke, por lo que una expresión de este tipo no puede ser el destino de una llamada al método
Una llamada a `Invoke` a través de un delegado ha fallado porque `Invoke` no está implementado en la clase de delegado.  
  
 **Identificador de error:** BC30220  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que se ha creado una instancia de la clase de delegado con una `Dim` instrucción y que se ha asignado un procedimiento a la instancia de delegado con el `AddressOf` operador.  
  
2.  Busque el código que implementa la clase de delegado y asegúrese de que implementa el `Invoke` procedimiento.  
  
## <a name="see-also"></a>Vea también
- [Delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [AddressOf (operador)](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)
