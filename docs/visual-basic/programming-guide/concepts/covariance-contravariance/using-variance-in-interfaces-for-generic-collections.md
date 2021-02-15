---
description: 'Más información sobre: usar la varianza en interfaces para colecciones genéricas (Visual Basic)'
title: Uso de la varianza en interfaces para colecciones genéricas
ms.date: 07/20/2015
ms.assetid: c867fcea-7462-4995-b9c5-542feec74036
ms.openlocfilehash: 9f98facbe1b89e468902384d2145fc5f91aae66a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100458985"
---
# <a name="using-variance-in-interfaces-for-generic-collections-visual-basic"></a><span data-ttu-id="13435-103">Usar la varianza en interfaces para las colecciones genéricas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13435-103">Using Variance in Interfaces for Generic Collections (Visual Basic)</span></span>

<span data-ttu-id="13435-104">Una interfaz covariante permite que sus métodos devuelvan tipos más derivados que los especificados en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="13435-104">A covariant interface allows its methods to return more derived types than those specified in the interface.</span></span> <span data-ttu-id="13435-105">Una interfaz contravariante permite que sus métodos acepten parámetros de tipos menos derivados que los especificados en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="13435-105">A contravariant interface allows its methods to accept parameters of less derived types than those specified in the interface.</span></span>

<span data-ttu-id="13435-106">Varias interfaces existentes en .NET Framework 4 pasaron a ser covariantes y contravariantes.</span><span class="sxs-lookup"><span data-stu-id="13435-106">In .NET Framework 4, several existing interfaces became covariant and contravariant.</span></span> <span data-ttu-id="13435-107">Por ejemplo, <xref:System.Collections.Generic.IEnumerable%601> y <xref:System.IComparable%601>.</span><span class="sxs-lookup"><span data-stu-id="13435-107">These include <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601>.</span></span> <span data-ttu-id="13435-108">Esto permite volver a usar métodos que funcionan con colecciones genéricas de tipos base para colecciones de tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="13435-108">This enables you to reuse methods that operate with generic collections of base types for collections of derived types.</span></span>

<span data-ttu-id="13435-109">Para obtener una lista de interfaces variantes en el .NET Framework, vea [varianza en interfaces genéricas (Visual Basic)](variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="13435-109">For a list of variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](variance-in-generic-interfaces.md).</span></span>

## <a name="converting-generic-collections"></a><span data-ttu-id="13435-110">Convertir colecciones genéricas</span><span class="sxs-lookup"><span data-stu-id="13435-110">Converting Generic Collections</span></span>

<span data-ttu-id="13435-111">En el ejemplo siguiente se muestran las ventajas de la compatibilidad con la covarianza en la interfaz <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="13435-111">The following example illustrates the benefits of covariance support in the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="13435-112">El método `PrintFullName` acepta una colección del tipo `IEnumerable(Of Person)` como parámetro.</span><span class="sxs-lookup"><span data-stu-id="13435-112">The `PrintFullName` method accepts a collection of the `IEnumerable(Of Person)` type as a parameter.</span></span> <span data-ttu-id="13435-113">Pero se puede volver a usar para una colección del tipo `IEnumerable(Of Person)` porque `Employee` hereda `Person`.</span><span class="sxs-lookup"><span data-stu-id="13435-113">However, you can reuse it for a collection of the `IEnumerable(Of Person)` type because `Employee` inherits `Person`.</span></span>

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

## <a name="comparing-generic-collections"></a><span data-ttu-id="13435-114">Comparar colecciones genéricas</span><span class="sxs-lookup"><span data-stu-id="13435-114">Comparing Generic Collections</span></span>

<span data-ttu-id="13435-115">En el ejemplo siguiente se muestran las ventajas de la compatibilidad con la contravarianza en la interfaz <xref:System.Collections.Generic.IComparer%601>.</span><span class="sxs-lookup"><span data-stu-id="13435-115">The following example illustrates the benefits of contravariance support in the <xref:System.Collections.Generic.IComparer%601> interface.</span></span> <span data-ttu-id="13435-116">La clase `PersonComparer` implementa la interfaz `IComparer(Of Person)`.</span><span class="sxs-lookup"><span data-stu-id="13435-116">The `PersonComparer` class implements the `IComparer(Of Person)` interface.</span></span> <span data-ttu-id="13435-117">Pero se puede volver a usar esta clase para comparar una secuencia de objetos del tipo `Employee` porque `Employee` hereda `Person`.</span><span class="sxs-lookup"><span data-stu-id="13435-117">However, you can reuse this class to compare a sequence of objects of the `Employee` type because `Employee` inherits `Person`.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="13435-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="13435-118">See also</span></span>

- [<span data-ttu-id="13435-119">Varianza en interfaces genéricas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13435-119">Variance in Generic Interfaces (Visual Basic)</span></span>](variance-in-generic-interfaces.md)
