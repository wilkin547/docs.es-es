---
title: La clase delegada '<classname>' no tiene ningún método Invoke y, por tanto, una expresión de este tipo no puede ser el destino de una llamada a método
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: e6ad06262806088347c94b3040b743618a3b3695
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874498"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>La clase delegada '\<classname>' no tiene ningún método Invoke y, por tanto, una expresión de este tipo no puede ser el destino de una llamada a método

No se pudo realizar una llamada a `Invoke` a través de un delegado porque `Invoke` no está implementado en la clase de delegado.  
  
 **Identificador de error:** BC30220  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Asegúrese de que se ha creado una instancia de la clase delegada con una `Dim` instrucción y que se ha asignado un procedimiento a la instancia de delegado con el `AddressOf` operador.  
  
2. Busque el código que implementa la clase delegada y asegúrese de que implementa el `Invoke` procedimiento.  
  
## <a name="see-also"></a>Consulte también

- [Delegados](../../programming-guide/language-features/delegates/index.md)
- [Delegate (Instrucción)](../statements/delegate-statement.md)
- [Operador AddressOf](../operators/addressof-operator.md)
- [Instrucción Dim](../statements/dim-statement.md)
