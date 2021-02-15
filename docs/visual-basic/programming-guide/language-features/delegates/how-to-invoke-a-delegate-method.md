---
description: 'Más información acerca de cómo: invocar un método delegado (Visual Basic)'
title: Procedimiento para invocar un método delegado
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: c5c20048969f2fef16b8b7f65e84a094a3f1cf9f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434477"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>Cómo: Invocar un método delegado (Visual Basic)

En este ejemplo se muestra cómo asociar un método a un delegado y, a continuación, invocar ese método a través del delegado.

### <a name="create-the-delegate-and-matching-procedures"></a>Crear el delegado y los procedimientos coincidentes

1. Cree un delegado denominado `MySubDelegate` .

    ```vb
    Delegate Sub MySubDelegate(ByVal x As Integer)
    ```

2. Declare una clase que contenga un método con la misma firma que el delegado.

    ```vb
    Class class1
        Sub Sub1(ByVal x As Integer)
            MsgBox("The value of x is: " & CStr(x))
        End Sub
    End Class
    ```

3. Defina un método que cree una instancia del delegado e invoque el método asociado al delegado llamando al `Invoke` método integrado.

    ```vb
    Protected Sub DelegateTest()
        Dim c1 As New class1
        ' Create an instance of the delegate.
        Dim msd As MySubDelegate = AddressOf c1.Sub1
        ' Call the method.
        msd.Invoke(10)
    End Sub
    ```

## <a name="see-also"></a>Consulte también

- [Delegate (Instrucción)](../../../language-reference/statements/delegate-statement.md)
- [Delegados](index.md)
- [Eventos](../events/index.md)
- [Aplicaciones multiproceso](../../../../standard/threading/using-threads-and-threading.md)
