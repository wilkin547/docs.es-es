---
title: 'Cómo: Invocar un método delegado (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: 9fea3ddbc9fb553041671713a64e4b866ee38b50
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392443"
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
 [Delegate (instrucción)](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Aplicaciones multiproceso](https://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)
