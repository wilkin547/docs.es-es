---
title: Procedimiento Calcular valores intermedios (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 933a97b2-dfe7-4f4d-94ad-e6e20df84abd
ms.openlocfilehash: cb619784d487ae12b1fb8bb3adc97acb0f767455
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61855453"
---
# <a name="how-to-calculate-intermediate-values-visual-basic"></a><span data-ttu-id="62c05-102">Procedimiento Calcular valores intermedios (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62c05-102">How to: Calculate Intermediate Values (Visual Basic)</span></span>
<span data-ttu-id="62c05-103">Este ejemplo muestra cómo calcular valores intermedios que se pueden usar para ordenar, filtrar y seleccionar.</span><span class="sxs-lookup"><span data-stu-id="62c05-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62c05-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="62c05-104">Example</span></span>  
 <span data-ttu-id="62c05-105">El siguiente ejemplo utiliza la cláusula `Let`.</span><span class="sxs-lookup"><span data-stu-id="62c05-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="62c05-106">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Datos numéricos (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="62c05-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
Dim extensions As IEnumerable(Of Decimal) = _  
    From el In root.<Data> _  
    Let extension = CDec(el.<Quantity>.Value) * CDec(el.<Price>.Value) _  
    Where extension > 25 _  
    Order By extension _  
    Select extension  
For Each ex As Decimal In extensions  
    Console.WriteLine(ex)  
Next  
```  
  
 <span data-ttu-id="62c05-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="62c05-107">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="62c05-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="62c05-108">Example</span></span>  
 <span data-ttu-id="62c05-109">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="62c05-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="62c05-110">Para obtener más información, consulte [trabajar con espacios de nombres XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="62c05-110">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="62c05-111">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Datos numéricos de un espacio de nombres](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="62c05-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns="http://www.adatum.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("DataInNamespace.xml")  
        Dim extensions As IEnumerable(Of Decimal) = _  
            From el In root.<Data> _  
            Let extension = CDec(el.<Quantity>.Value) * CDec(el.<Price>.Value) _  
            Where extension > 25 _  
            Order By extension _  
            Select extension  
        For Each ex As Decimal In extensions  
            Console.WriteLine(ex)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="62c05-112">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="62c05-112">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="see-also"></a><span data-ttu-id="62c05-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="62c05-113">See also</span></span>

- [<span data-ttu-id="62c05-114">Consultas básicas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62c05-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
