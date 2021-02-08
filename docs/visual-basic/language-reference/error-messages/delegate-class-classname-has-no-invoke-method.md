---
description: "Más información sobre: BC30220: la clase delegada ' <classname> ' no tiene un método Invoke, por lo que una expresión de este tipo no puede ser el destino de una llamada al método"
title: La clase delegada '<classname>' no tiene ningún método Invoke y, por tanto, una expresión de este tipo no puede ser el destino de una llamada a método
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: c0d3f6e352a98e194b2c2ddca04bfa7254ec37a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796631"
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
