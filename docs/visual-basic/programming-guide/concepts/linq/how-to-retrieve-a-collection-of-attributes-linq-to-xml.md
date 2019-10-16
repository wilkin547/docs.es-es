---
title: 'Cómo: recuperar una colección de atributos (LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: a07e9645-b45b-403b-b698-f652f904c7d2
ms.openlocfilehash: 7c0f809c5a0707f2e6575cb8bca1b2a312f6daeb
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321323"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-visual-basic"></a><span data-ttu-id="f3cd4-102">Cómo: recuperar una colección de atributos (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3cd4-102">How to: Retrieve a Collection of Attributes (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="f3cd4-103">En este tema se presenta el método <xref:System.Xml.Linq.XElement.Attributes%2A>.</span><span class="sxs-lookup"><span data-stu-id="f3cd4-103">This topic introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="f3cd4-104">Este método recupera los atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="f3cd4-104">This method retrieves the attributes of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3cd4-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3cd4-105">Example</span></span>  
 <span data-ttu-id="f3cd4-106">En el ejemplo siguiente se muestra cómo procesar una iteración en la colección de atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="f3cd4-106">The following example shows how to iterate through the collection of attributes of an element.</span></span>  
  
```vb  
Dim val = _  
    <Value ID="1243" Type="int" ConvertableTo="double">100</Value>  
Dim listOfAttributes As IEnumerable(Of XAttribute) = _  
    From att In val.Attributes() _  
    Select att  
For Each att As XAttribute In listOfAttributes  
    Console.WriteLine(att)  
Next  
```  
  
 <span data-ttu-id="f3cd4-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="f3cd4-107">This code produces the following output:</span></span>  
  
```console  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3cd4-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3cd4-108">See also</span></span>

- [<span data-ttu-id="f3cd4-109">Ejes de LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3cd4-109">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
