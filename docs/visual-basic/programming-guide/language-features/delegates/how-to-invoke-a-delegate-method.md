---
title: "C&#243;mo: Invocar un m&#233;todo delegado (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# C&#243;mo: Invocar un m&#233;todo delegado (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Este ejemplo muestra cómo asociar un método a un delegado e invocar luego este método a través del delegado.  
  
### Cree el delegado y los procedimientos correspondientes  
  
1.  Cree un delegado denominado `MySubDelegate`.  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  Declare una clase que contenga un método con la misma firma que el delegado.  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  Defina un método que cree una instancia del delegado e invoque el método asociado al delegado llamando al método `Invoke` integrado.  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## Vea también  
 [Delegate \(Instrucción\)](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/events.md)   
 [Aplicaciones multiproceso](../Topic/Multithreaded%20Applications%20\(C%23%20and%20Visual%20Basic\).md)