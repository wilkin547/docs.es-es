---
title: La clase delegada '<classname>' no tiene ningún método Invoke y, por tanto, una expresión de este tipo no puede ser el destino de una llamada a método
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 4e0fc61c7356008755134f670fa1fab0165cfd48
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162796"
---
# <a name="bc30220-delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>BC30220: la clase delegada ' \<classname> ' no tiene un método Invoke, por lo que una expresión de este tipo no puede ser el destino de una llamada al método

No se pudo realizar una llamada a `Invoke` a través de un delegado porque `Invoke` no está implementado en la clase de delegado.

 **Identificador de error:** BC30220

## <a name="to-correct-this-error"></a>Para corregir este error

1. Asegúrese de que se ha creado una instancia de la clase delegada con una `Dim` instrucción y que se ha asignado un procedimiento a la instancia de delegado con el `AddressOf` operador.

2. Busque el código que implementa la clase delegada y asegúrese de que implementa el `Invoke` procedimiento.

## <a name="see-also"></a>Vea también

- [Delegados](../../programming-guide/language-features/delegates/index.md)
- [Delegate (Instrucción)](../statements/delegate-statement.md)
- [Operador AddressOf](../operators/addressof-operator.md)
- [Instrucción Dim](../statements/dim-statement.md)
