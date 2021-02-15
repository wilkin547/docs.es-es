---
description: "Más información sobre: BC30154: <type1> ' <typename> ' debe implementar ' <membername> ' para la interfaz ' <interfacename> '"
title: <type1>"<typename>" debe implementar "<membername>" para la interfaz "<interfacename>"
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: fc0cf8544984ddf41f1f91cb0bca90b630d9614d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100473568"
---
# <a name="bc30154-type1typename-must-implement-membername-for-interface-interfacename"></a>BC30154: \<type1> ' \<typename> ' debe implementar ' \<membername> ' para la interfaz ' \<interfacename> '

' \<typename> ' debe implementar ' \<membername> ' para la interfaz ' \<interfacename> '. La implementación de la propiedad debe tener especificadores ' ReadOnly '/' WriteOnly ' coincidentes.

 Una clase o estructura notifica a que implemente una interfaz pero no implementa un procedimiento, una propiedad o un evento definidos por la interfaz. Se deben implementar todos los miembros de la interfaz.

 **Identificador de error:** BC30154

## <a name="to-correct-this-error"></a>Para corregir este error

1. Declare un miembro con el mismo nombre y la misma signatura que el definido en la interfaz. Asegúrese de incluir al menos la `End Function` instrucción, `End Sub` o `End Property` .

2. Agregue una `Implements` cláusula al final de la `Function` instrucción, `Sub` , `Property` o `Event` . Por ejemplo:

    ```vb
    Public Event ItHappened() Implements IBaseInterface.ItHappened
    ```

3. Al implementar una propiedad, asegúrese de que `ReadOnly` o `WriteOnly` se utiliza de la misma manera que en la definición de la interfaz.

4. Al implementar una propiedad, declare `Get` `Set` los procedimientos y, según corresponda.

## <a name="see-also"></a>Consulte también

- [Implements (Instrucción)](../statements/implements-statement.md)
- [Interfaces](../../programming-guide/language-features/interfaces/index.md)
