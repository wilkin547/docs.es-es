---
title: "Usar la varianza en Interfaces para las colecciones genéricas (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: c867fcea-7462-4995-b9c5-542feec74036
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 86184c7de3fe16148bf954b16d703ca682216337
ms.lasthandoff: 03/13/2017

---
# <a name="using-variance-in-interfaces-for-generic-collections-visual-basic"></a>Usar la varianza en Interfaces para las colecciones genéricas (Visual Basic)
Una interfaz covariante permite que sus métodos devuelvan tipos más derivados que los especificados en la interfaz. Una interfaz contravariante permite que sus métodos acepten parámetros de menos tipos derivados que los especificados en la interfaz.  
  
 En .NET Framework 4, varias interfaces existentes, empezaron a estar covariantes y contravariante. Estos incluyen <xref:System.Collections.Generic.IEnumerable%601>y <xref:System.IComparable%601>.</xref:System.IComparable%601> </xref:System.Collections.Generic.IEnumerable%601> Esto permite reutilizar los métodos que funcionan con colecciones genéricas de tipos base para las colecciones de tipos derivados.  
  
 Para obtener una lista de interfaces variantes de .NET Framework, vea [varianza en Interfaces genéricas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).  
  
## <a name="converting-generic-collections"></a>Convertir colecciones genéricas  
 En el ejemplo siguiente se muestra las ventajas de la compatibilidad con la covarianza en la <xref:System.Collections.Generic.IEnumerable%601>interfaz.</xref:System.Collections.Generic.IEnumerable%601> El `PrintFullName` método acepta una colección de los `IEnumerable(Of Person)` tipo como parámetro. Sin embargo, se puede reutilizar para una colección de la `IEnumerable(Of Person)` tipo porque `Employee` hereda `Person`.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## <a name="comparing-generic-collections"></a>Comparar colecciones genéricas  
 En el ejemplo siguiente se muestra las ventajas de la compatibilidad con la contravarianza en el <xref:System.Collections.Generic.IComparer%601>interfaz.</xref:System.Collections.Generic.IComparer%601> La clase `PersonComparer` implementa la interfaz `IComparer(Of Person)`. Sin embargo, puede volver a usar esta clase para comparar una secuencia de objetos de la `Employee` tipo porque `Employee` hereda `Person`.  
  
```vb  
' Simple hierarhcy of classes.  
Public Class Person  
    Public Property FirstName As String  
    Public Property LastName As String  
End Class  
  
Public Class Employee  
    Inherits Person  
End Class  
' The custom comparer for the Person type  
' with standard implementations of Equals()  
' and GetHashCode() methods.  
Class PersonComparer  
    Implements IEqualityComparer(Of Person)  
  
    Public Function Equals1(  
        ByVal x As Person,  
        ByVal y As Person) As Boolean _  
        Implements IEqualityComparer(Of Person).Equals  
  
        If x Is y Then Return True  
        If x Is Nothing OrElse y Is Nothing Then Return False  
        Return (x.FirstName = y.FirstName) AndAlso  
            (x.LastName = y.LastName)  
    End Function  
    Public Function GetHashCode1(  
        ByVal person As Person) As Integer _  
        Implements IEqualityComparer(Of Person).GetHashCode  
  
        If person Is Nothing Then Return 0  
        Dim hashFirstName =  
            If(person.FirstName Is Nothing,  
            0, person.FirstName.GetHashCode())  
        Dim hashLastName = person.LastName.GetHashCode()  
        Return hashFirstName Xor hashLastName  
    End Function  
End Class  
  
Sub Main()  
    Dim employees = New List(Of Employee) From {  
        New Employee With {.FirstName = "Michael", .LastName = "Alexander"},  
        New Employee With {.FirstName = "Jeff", .LastName = "Price"}  
    }  
  
    ' You can pass PersonComparer,   
    ' which implements IEqualityComparer(Of Person),  
    ' although the method expects IEqualityComparer(Of Employee)  
  
    Dim noduplicates As IEnumerable(Of Employee) = employees.Distinct(New PersonComparer())  
  
    For Each employee In noduplicates  
        Console.WriteLine(employee.FirstName & " " & employee.LastName)  
    Next  
End Sub  
```  
  
## <a name="see-also"></a>Vea también  
 [Varianza en Interfaces genéricas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
