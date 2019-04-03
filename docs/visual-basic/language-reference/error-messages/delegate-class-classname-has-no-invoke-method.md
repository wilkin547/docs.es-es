---
title: La clase delegada '<classname>' no tiene ningún método Invoke y, por tanto, una expresión de este tipo no puede ser el destino de una llamada a método
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 463b4f50e8c431bbbc113509e5fd9dd1756b5928
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822523"
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
