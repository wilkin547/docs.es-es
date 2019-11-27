---
title: 'Cómo: Invocar un método delegado'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: 520bacfbe6103490e0459cd5af149c1d55a8fce4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345265"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>Cómo: Invocar un método delegado (Visual Basic)

En este ejemplo se muestra cómo asociar un método a un delegado y, a continuación, invocar ese método a través del delegado.

### <a name="create-the-delegate-and-matching-procedures"></a>Crear el delegado y los procedimientos coincidentes

1. Cree un delegado denominado `MySubDelegate`.

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

3. Defina un método que cree una instancia del delegado e invoque el método asociado al delegado llamando al método integrado `Invoke`.

    ```vb
    Protected Sub DelegateTest()
        Dim c1 As New class1
        ' Create an instance of the delegate.
        Dim msd As MySubDelegate = AddressOf c1.Sub1
        ' Call the method.
        msd.Invoke(10)
    End Sub
    ```

## <a name="see-also"></a>Vea también

- [Delegate (instrucción)](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Aplicaciones multiproceso](../../../../standard/threading/using-threads-and-threading.md)
