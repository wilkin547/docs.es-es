---
description: "Más información sobre: BC30154: <type1> ' <typename> ' debe implementar ' <membername> ' para la interfaz '<interfacename>"
title: <type1>"<typename>" debe implementar "<membername>" para la interfaz "<interfacename>"
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: fc47aaef0477638e0e1a566bca23e9c35cf514f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641153"
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

## <a name="see-also"></a>Vea también

- [Implements (Instrucción)](../statements/implements-statement.md)
- [Interfaces](../../programming-guide/language-features/interfaces/index.md)
