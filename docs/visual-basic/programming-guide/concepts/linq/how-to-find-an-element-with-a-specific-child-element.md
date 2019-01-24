---
title: Procedimiento Buscar un elemento con un elemento secundario específico (Visual Basic)
ms.date: 07/20/2015
ms.assetid: b0d0a463-6a85-46c3-8453-ad25b0ecf93c
ms.openlocfilehash: c9239ed5ff417b66cebeb3015014f1498278b602
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659087"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-visual-basic"></a><span data-ttu-id="c949f-102">Procedimiento Buscar un elemento con un elemento secundario específico (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c949f-102">How to: Find an Element with a Specific Child Element (Visual Basic)</span></span>
<span data-ttu-id="c949f-103">Este tema muestra cómo encontrar un elemento en particular que tenga un elemento secundario con un valor específico.</span><span class="sxs-lookup"><span data-stu-id="c949f-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c949f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c949f-104">Example</span></span>  
 <span data-ttu-id="c949f-105">El ejemplo busca el elemento `Test` que tenga un elemento secundario `CommandLine` con el valor de "Examp2.EXE".</span><span class="sxs-lookup"><span data-stu-id="c949f-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="c949f-106">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Probar configuración (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c949f-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("TestConfig.xml")  
Dim tests As IEnumerable(Of XElement) = _  
    From el In root.<Test> _  
    Where el.<CommandLine>.Value = "Examp2.EXE" _  
    Select el  
For Each el as XElement In tests  
    Console.WriteLine(el.@TestId)  
Next  
```  
  
 <span data-ttu-id="c949f-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c949f-107">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
 <span data-ttu-id="c949f-108">Tenga en cuenta que este ejemplo se usa el [propiedad de eje secundario XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), [propiedad de eje de atributo XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)y el [propiedad Value de XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="c949f-108">Note that this example uses the [XML Child axis property](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), the [XML Attribute axis property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md), and the [XML Value property](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c949f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c949f-109">Example</span></span>  
 <span data-ttu-id="c949f-110">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c949f-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="c949f-111">Para obtener más información, consulte [trabajar con espacios de nombres XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="c949f-111">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="c949f-112">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Configuración de prueba en un Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="c949f-112">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("TestConfigInNamespace.xml")  
        Dim tests As IEnumerable(Of XElement) = _  
            From el In root.<Test> _  
            Where el.<CommandLine>.Value = "Examp2.EXE" _  
            Select el  
        For Each el As XElement In tests  
            Console.WriteLine(el.@TestId)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="c949f-113">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c949f-113">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="c949f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c949f-114">See also</span></span>
- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="c949f-115">Consultas básicas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c949f-115">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
- [<span data-ttu-id="c949f-116">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c949f-116">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="c949f-117">Operaciones de proyección (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c949f-117">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
