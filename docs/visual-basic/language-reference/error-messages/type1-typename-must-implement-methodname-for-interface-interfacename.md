---
title: <type1>'<typename>'debe implementar'<methodname>'para la interfaz'<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 432f089bc77928308820d7456d930fba8dc513f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304914"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a>\<tipo1 >'\<typename >' debe implementar '\<methodname >' para la interfaz '\<interfacename >'
Una clase o estructura intenta implementar una interfaz, pero no implementa un procedimiento definido por la interfaz. Se deben implementar todos los miembros de la interfaz.  
  
 **Identificador de error:** BC30149  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Declare un procedimiento con el mismo nombre y firma, tal como se define en la interfaz. No olvide incluir al menos el `End Function` o `End Sub` instrucción.  
  
2. Agregar un `Implements` cláusula al final de la `Function` o `Sub` instrucción. Por ejemplo:  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>Vea también

- [Implements (instrucción)](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
