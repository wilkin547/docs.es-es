---
title: 'Cómo: Proyectar un nuevo tipo (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 8cfb24f5-89b2-4cfb-b85d-e7963f8f1845
ms.openlocfilehash: a2486d88af537fb4aa8f34243a5a739d25ee5be1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353332"
---
# <a name="how-to-project-a-new-type-linq-to-xml-visual-basic"></a><span data-ttu-id="0048e-102">How to: Project a New Type (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0048e-102">How to: Project a New Type (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="0048e-103">Otros ejemplos de esta sección han mostrado consultados que devuelven resultados como <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> de `string` y <xref:System.Collections.Generic.IEnumerable%601> de `int`.</span><span class="sxs-lookup"><span data-stu-id="0048e-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="0048e-104">Se trata de tipos de resultados comunes, pero no son adecuados para cada caso.</span><span class="sxs-lookup"><span data-stu-id="0048e-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="0048e-105">En muchos casos querrá que sus consultas devuelvan un <xref:System.Collections.Generic.IEnumerable%601> de algún otro tipo.</span><span class="sxs-lookup"><span data-stu-id="0048e-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0048e-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0048e-106">Example</span></span>  
 <span data-ttu-id="0048e-107">En este ejemplo se muestra como crear instancias de objetos en la cláusula `Select`.</span><span class="sxs-lookup"><span data-stu-id="0048e-107">This example shows how to instantiate objects in the `Select` clause.</span></span> <span data-ttu-id="0048e-108">El código primero define una nueva clase con un constructor y después modifica la instrucción `Select` para que la expresión sea una nueva instancia de la nueva clase.</span><span class="sxs-lookup"><span data-stu-id="0048e-108">The code first defines a new class with a constructor, and then modifies the `Select` statement so that the expression is a new instance of the new class.</span></span>  
  
 <span data-ttu-id="0048e-109">En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0048e-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Public Class NameQty  
    Public name As String  
    Public qty As Integer  
    Public Sub New(ByVal n As String, ByVal q As Integer)  
        name = n  
        qty = q  
    End Sub  
End Class  
  
Public Class Program  
    Shared Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
  
        Dim nqList As IEnumerable(Of NameQty) = _  
            From n In po...<Item> _  
            Select New NameQty( _  
                n.<ProductName>.Value, CInt(n.<Quantity>.Value))  
  
        For Each n As NameQty In nqList  
            Console.WriteLine(n.name & ":" & n.qty)  
        Next  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="0048e-110">This example uses the `M:System.Xml.Linq.XElement.Element` method that was introduced in the topic [How to: Retrieve a Single Child Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0048e-110">This example uses the `M:System.Xml.Linq.XElement.Element` method that was introduced in the topic [How to: Retrieve a Single Child Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="0048e-111">También utiliza conversiones para recuperar los valores de los elementos devueltos por el método `M:System.Xml.Linq.XElement.Element`.</span><span class="sxs-lookup"><span data-stu-id="0048e-111">It also uses casts to retrieve the values of the elements that are returned by the `M:System.Xml.Linq.XElement.Element` method.</span></span>  
  
 <span data-ttu-id="0048e-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0048e-112">This example produces the following output:</span></span>  
  
```console  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a><span data-ttu-id="0048e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0048e-113">See also</span></span>

- [<span data-ttu-id="0048e-114">Projections and Transformations (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0048e-114">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
