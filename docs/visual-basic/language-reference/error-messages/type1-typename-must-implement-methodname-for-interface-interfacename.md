---
title: <type1>"<typename>" debe implementar "<methodname>" para la interfaz "<interfacename>"
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 8bf8872277ec901e066a8b950aaf3e61babfcc48
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872111"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a>\<type1>"\<typename>" debe implementar "\<methodname>" para la interfaz "\<interfacename>"

Una clase o estructura notifica a que implemente una interfaz pero no implementa un procedimiento definido por la interfaz. Se deben implementar todos los miembros de la interfaz.  
  
 **Identificador de error:** BC30149  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Declare un procedimiento con el mismo nombre y la misma signatura que el definido en la interfaz. Asegúrese de incluir al menos la `End Function` instrucción o `End Sub` .  
  
2. Agregue una `Implements` cláusula al final de la `Function` instrucción o `Sub` . Por ejemplo:  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>Consulte también

- [Implements (Instrucción)](../statements/implements-statement.md)
- [Interfaces](../../programming-guide/language-features/interfaces/index.md)
