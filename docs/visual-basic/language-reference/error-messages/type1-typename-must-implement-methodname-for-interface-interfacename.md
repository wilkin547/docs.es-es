---
description: "Más información sobre: BC30149: <type1> ' <typename> ' debe implementar ' <methodname> ' para la interfaz '<interfacename>"
title: <type1>"<typename>" debe implementar "<methodname>" para la interfaz "<interfacename>"
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 34635cbe5b8736d273d5972a1bb83aa3d975490b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99675018"
---
# <a name="bc30149-type1typename-must-implement-methodname-for-interface-interfacename"></a>BC30149: \<type1> ' \<typename> ' debe implementar ' \<methodname> ' para la interfaz ' \<interfacename> '

Una clase o estructura notifica a que implemente una interfaz pero no implementa un procedimiento definido por la interfaz. Se deben implementar todos los miembros de la interfaz.

 **Identificador de error:** BC30149

## <a name="to-correct-this-error"></a>Para corregir este error

1. Declare un procedimiento con el mismo nombre y la misma signatura que el definido en la interfaz. Asegúrese de incluir al menos la `End Function` instrucción o `End Sub` .

2. Agregue una `Implements` cláusula al final de la `Function` instrucción o `Sub` . Por ejemplo:

    ```vb
    Public Sub DoSomething() Implements IBaseInterface.DoSomething
    ```

## <a name="see-also"></a>Vea también

- [Implements (Instrucción)](../statements/implements-statement.md)
- [Interfaces](../../programming-guide/language-features/interfaces/index.md)
