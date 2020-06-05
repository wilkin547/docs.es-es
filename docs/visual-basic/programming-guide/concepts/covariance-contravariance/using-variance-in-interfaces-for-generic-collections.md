---
title: Uso de la varianza en interfaces para colecciones genéricas
ms.date: 07/20/2015
ms.assetid: c867fcea-7462-4995-b9c5-542feec74036
ms.openlocfilehash: b762ce42215f9b24371313446637e95962677bfb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375646"
---
# <a name="using-variance-in-interfaces-for-generic-collections-visual-basic"></a>Usar la varianza en interfaces para las colecciones genéricas (Visual Basic)

Una interfaz covariante permite que sus métodos devuelvan tipos más derivados que los especificados en la interfaz. Una interfaz contravariante permite que sus métodos acepten parámetros de tipos menos derivados que los especificados en la interfaz.

Varias interfaces existentes en .NET Framework 4 pasaron a ser covariantes y contravariantes. Por ejemplo, <xref:System.Collections.Generic.IEnumerable%601> y <xref:System.IComparable%601>. Esto permite volver a usar métodos que funcionan con colecciones genéricas de tipos base para colecciones de tipos derivados.

Para obtener una lista de interfaces variantes en el .NET Framework, vea [varianza en interfaces genéricas (Visual Basic)](variance-in-generic-interfaces.md).

## <a name="converting-generic-collections"></a>Convertir colecciones genéricas

En el ejemplo siguiente se muestran las ventajas de la compatibilidad con la covarianza en la interfaz <xref:System.Collections.Generic.IEnumerable%601>. El método `PrintFullName` acepta una colección del tipo `IEnumerable(Of Person)` como parámetro. Pero se puede volver a usar para una colección del tipo `IEnumerable(Of Person)` porque `Employee` hereda `Person`.

```vb
' Simple hierarchy of classes.
Public Class Person
    Public Property FirstName As String
    Public Property LastName As String
End Class

Public Class Employee
    Inherits Person
End Class

' The method has a parameter of the IEnumerable(Of Person) type.
Public Sub PrintFullName(ByVal persons As IEnumerable(Of Person))
    For Each person As Person In persons
        Console.WriteLine(
            "Name: " & person.FirstName & " " & person.LastName)
    Next
End Sub

Sub Main()
    Dim employees As IEnumerable(Of Employee) = New List(Of Employee)

    ' You can pass IEnumerable(Of Employee),
    ' although the method expects IEnumerable(Of Person).

    PrintFullName(employees)

End Sub
```

## <a name="comparing-generic-collections"></a>Comparar colecciones genéricas

En el ejemplo siguiente se muestran las ventajas de la compatibilidad con la contravarianza en la interfaz <xref:System.Collections.Generic.IComparer%601>. La clase `PersonComparer` implementa la interfaz `IComparer(Of Person)`. Pero se puede volver a usar esta clase para comparar una secuencia de objetos del tipo `Employee` porque `Employee` hereda `Person`.

```vb
' Simple hierarchy of classes.
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

- [Varianza en interfaces genéricas (Visual Basic)](variance-in-generic-interfaces.md)
