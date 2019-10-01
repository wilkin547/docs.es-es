---
title: <type1>"<typename>" debe implementar "<membername>" para la interfaz "<interfacename>"
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: a824b66eaad964049ced5cae5eb2cc370d00ba7f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696890"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a>\<type1 > ' \<typename > ' debe implementar ' \<membername > ' para la interfaz ' \<interfacename > '
' \<typename > ' debe implementar ' \<membername > ' para la interfaz ' \<interfacename > '. La implementación de la propiedad debe tener especificadores ' ReadOnly '/' WriteOnly ' coincidentes.  
  
 Una clase o estructura notifica a que implemente una interfaz pero no implementa un procedimiento, una propiedad o un evento definidos por la interfaz. Se deben implementar todos los miembros de la interfaz.  
  
 **IDENTIFICADOR de error:** BC30154  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Declare un miembro con el mismo nombre y la misma signatura que el definido en la interfaz. Asegúrese de incluir al menos la instrucción `End Function`, `End Sub` o `End Property`.  
  
2. Agregue una cláusula `Implements` al final de la instrucción `Function`, `Sub`, `Property` o `Event`. Por ejemplo:  
  
    ```vb  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. Al implementar una propiedad, asegúrese de que `ReadOnly` o `WriteOnly` se utiliza de la misma manera que en la definición de la interfaz.  
  
4. Al implementar una propiedad, declare @no__t los procedimientos-0 y `Set`, según corresponda.  
  
## <a name="see-also"></a>Vea también

- [Implements (instrucción)](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
