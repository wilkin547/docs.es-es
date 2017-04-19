---
title: "Usar la varianza para los delegados genéricos Func y Action (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 36c3012f-b39c-493b-b90f-079b5912ac1b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 28c3f84d21f9fbc7e57ba079461194acf7612add
ms.lasthandoff: 03/13/2017

---
# <a name="using-variance-for-func-and-action-generic-delegates-visual-basic"></a>Usar la varianza para Func y Action Generic Delegates (Visual Basic)
Estos ejemplos muestra cómo usar la covarianza y contravarianza en los `Func` y `Action` delegados genéricos para habilitar la reutilización de métodos y proporcionan más flexibilidad en el código.  
  
 Para obtener más información sobre la covarianza y contravarianza, consulte [varianza en delegados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).  
  
## <a name="using-delegates-with-covariant-type-parameters"></a>Usar a delegados con parámetros de tipo covariante  
 En el ejemplo siguiente se muestra las ventajas de la compatibilidad con la covarianza en la interfaz genérica `Func` delegados. El `FindByTitle` método toma un parámetro de la `String` tipo y devuelve un objeto de la `Employee` tipo. Sin embargo, puede asignar este método para el `Func(Of String, Person)` delegado porque `Employee` hereda `Person`.  
  
```vb  
' Simple hierarchy of classes.  
Public Class Person  
End Class  
  
Public Class Employee  
    Inherits Person  
End Class  
  
Class Finder  
    Public Shared Function FindByTitle(  
        ByVal title As String) As Employee  
        ' This is a stub for a method that returns  
        ' an employee that has the specified title.  
        Return New Employee  
    End Function  
  
    Sub Test()  
        ' Create an instance of the delegate without using variance.  
        Dim findEmployee As Func(Of String, Employee) =  
            AddressOf FindByTitle  
  
        ' The delegate expects a method to return Person,  
        ' but you can assign it a method that returns Employee.  
        Dim findPerson As Func(Of String, Person) =  
            AddressOf FindByTitle  
  
        ' You can also assign a delegate   
        ' that returns a more derived type to a delegate   
        ' that returns a less derived type.  
        findPerson = findEmployee  
    End Sub  
End Class  
```  
  
## <a name="using-delegates-with-contravariant-type-parameters"></a>Usar a delegados con parámetros de tipo contravariante  
 En el ejemplo siguiente se muestra las ventajas de la compatibilidad con la contravarianza en la interfaz genérica `Action` delegados. El `AddToContacts` método toma un parámetro de la `Person` tipo. Sin embargo, puede asignar este método para el `Action(Of Employee)` delegado porque `Employee` hereda `Person`.  
  
```vb  
Public Class Person  
End Class  
  
Public Class Employee  
    Inherits Person  
End Class  
  
Class AddressBook  
    Shared Sub AddToContacts(ByVal person As Person)  
        ' This method adds a Person object  
        ' to a contact list.  
    End Sub  
  
    Sub Test()  
        ' Create an instance of the delegate without using variance.  
        Dim addPersonToContacts As Action(Of Person) =  
            AddressOf AddToContacts  
  
        ' The Action delegate expects   
        ' a method that has an Employee parameter,  
        ' but you can assign it a method that has a Person parameter  
        ' because Employee derives from Person.  
        Dim addEmployeeToContacts As Action(Of Employee) =  
            AddressOf AddToContacts  
  
        ' You can also assign a delegate   
        ' that accepts a less derived parameter   
        ' to a delegate that accepts a more derived parameter.  
        addEmployeeToContacts = addPersonToContacts  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a>Vea también  
 [Covarianza y contravarianza (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/covariance-and-contravariance.md)   
 [Genéricos](https://msdn.microsoft.com/library/ms172192)
