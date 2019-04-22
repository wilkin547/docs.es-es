---
title: Procedimiento Controlar el tipo de una proyección (Visual Basic)
ms.date: 07/20/2015
ms.assetid: a0171276-0b46-4817-aee5-a8d5191b12fe
ms.openlocfilehash: dd09914a75a8d4b20ddf9ff452f046bf7671152f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831410"
---
# <a name="how-to-control-the-type-of-a-projection-visual-basic"></a><span data-ttu-id="99a6c-102">Procedimiento Controlar el tipo de una proyección (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99a6c-102">How to: Control the Type of a Projection (Visual Basic)</span></span>
<span data-ttu-id="99a6c-103">La proyección es el proceso de tomar un conjunto de datos, filtrarlo, cambiar su forma e incluso cambiar su tipo.</span><span class="sxs-lookup"><span data-stu-id="99a6c-103">Projection is the process of taking one set of data, filtering it, changing its shape, and even changing its type.</span></span> <span data-ttu-id="99a6c-104">La mayoría de las expresiones de consulta realizan proyecciones.</span><span class="sxs-lookup"><span data-stu-id="99a6c-104">Most query expressions perform projections.</span></span> <span data-ttu-id="99a6c-105">La mayor parte de las expresiones de consulta de esta sección se evalúan como <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>, aunque puede controlar el tipo de proyección para crear colecciones de otros tipos.</span><span class="sxs-lookup"><span data-stu-id="99a6c-105">Most of the query expressions shown in this section evaluate to <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, but you can control the type of the projection to create collections of other types.</span></span> <span data-ttu-id="99a6c-106">En este tema se explica cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="99a6c-106">This topic shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99a6c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99a6c-107">Example</span></span>  
 <span data-ttu-id="99a6c-108">En el ejemplo siguiente, se define un nuevo tipo, `Customer`.</span><span class="sxs-lookup"><span data-stu-id="99a6c-108">The following example defines a new type, `Customer`.</span></span> <span data-ttu-id="99a6c-109">La expresión de consulta crea una instancia de nuevos objetos `Customer` en la cláusula `Select`.</span><span class="sxs-lookup"><span data-stu-id="99a6c-109">The query expression then instantiates new `Customer` objects in the `Select` clause.</span></span> <span data-ttu-id="99a6c-110">Esto hace que el tipo de la expresión de consulta sea <xref:System.Collections.Generic.IEnumerable%601> de `Customer`.</span><span class="sxs-lookup"><span data-stu-id="99a6c-110">This causes the type of the query expression to be <xref:System.Collections.Generic.IEnumerable%601> of `Customer`.</span></span>  
  
 <span data-ttu-id="99a6c-111">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Clientes y pedidos (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="99a6c-111">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
```vb  
Public Class Customer  
    Private customerIDValue As String  
    Public Property CustomerID() As String  
        Get  
            Return customerIDValue  
        End Get  
        Set(ByVal value As String)  
            customerIDValue = value  
        End Set  
    End Property  
  
    Private companyNameValue As String  
    Public Property CompanyName() As String  
        Get  
            Return companyNameValue  
        End Get  
        Set(ByVal value As String)  
            companyNameValue = value  
        End Set  
    End Property  
  
    Private contactNameValue As String  
    Public Property ContactName() As String  
        Get  
            Return contactNameValue  
        End Get  
        Set(ByVal value As String)  
            contactNameValue = value  
        End Set  
    End Property  
  
    Public Sub New(ByVal customerID As String, _  
                   ByVal companyName As String, _  
                   ByVal contactName As String)  
        CustomerIDValue = customerID  
        CompanyNameValue = companyName  
        ContactNameValue = contactName  
    End Sub  
  
    Public Overrides Function ToString() As String  
        Return String.Format("{0}:{1}:{2}", Me.CustomerID, Me.CompanyName, Me.ContactName)  
    End Function  
End Class  
  
Sub Main()  
    Dim custOrd As XElement = XElement.Load("CustomersOrders.xml")  
    Dim custList As IEnumerable(Of Customer) = _  
        From el In custOrd.<Customers>.<Customer> _  
        Select New Customer( _  
            el.@<CustomerID>, _  
            el.<CompanyName>.Value, _  
            el.<ContactName>.Value _  
        )  
    For Each cust In custList  
        Console.WriteLine(cust)  
    Next  
End Sub  
```  
  
 <span data-ttu-id="99a6c-112">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="99a6c-112">This code produces the following output:</span></span>  
  
```  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a><span data-ttu-id="99a6c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="99a6c-113">See also</span></span>

- <xref:System.Linq.Enumerable.Select%2A>
- [<span data-ttu-id="99a6c-114">Proyecciones y transformaciones (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99a6c-114">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
