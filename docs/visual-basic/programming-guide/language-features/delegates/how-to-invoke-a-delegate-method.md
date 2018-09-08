---
title: 'Cómo: Invocar un método delegado (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: c50a32d300aaf52efe0c55cef69d5793a98305ac
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44204611"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>Cómo: Invocar un método delegado (Visual Basic)
En este ejemplo se muestra cómo asociar un método con un delegado y, a continuación, se invoca ese método a través del delegado.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Crear el delegado y los procedimientos correspondientes  
  
1.  Cree un delegado denominado `MySubDelegate`.  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  Declare una clase que contiene un método con la misma firma que el delegado.  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  Defina un método que crea una instancia del delegado e invoca el método asociado con el delegado mediante una llamada a la integrada `Invoke` método.  
  
    ```  
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
