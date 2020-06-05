---
title: <type1>"<typename>" debe implementar "<membername>" para la interfaz "<interfacename>"
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 4ffe18e11c388a8c69ef0592bde1b78f5b219680
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386859"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a>\<type1>"\<typename>" debe implementar "\<membername>" para la interfaz "\<interfacename>"
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
