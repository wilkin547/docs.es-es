---
title: 'Cómo: escribir una consulta que busca elementos basados en contexto (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 0b085290-ddc1-4126-aaa0-e4c95a3d9a09
ms.openlocfilehash: a16f591fc08e8822059bae2ee07d96af575059bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33645686"
---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-visual-basic"></a><span data-ttu-id="6419b-102">Cómo: escribir una consulta que busca elementos basados en contexto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6419b-102">How to: Write a Query that Finds Elements Based on Context (Visual Basic)</span></span>
<span data-ttu-id="6419b-103">Es posible que alguna vez tenga que escribir una consulta que seleccione elementos basándose en su contexto.</span><span class="sxs-lookup"><span data-stu-id="6419b-103">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="6419b-104">Quizás desea filtrar basándose en elementos de mismo nivel precedentes o siguientes.</span><span class="sxs-lookup"><span data-stu-id="6419b-104">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="6419b-105">Quizás desea filtrar basándose e elementos secundarios o elementos antecesores.</span><span class="sxs-lookup"><span data-stu-id="6419b-105">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="6419b-106">Puede hacerlo escribiendo una consulta y utilizando los resultados de la consulta en la cláusula `where`.</span><span class="sxs-lookup"><span data-stu-id="6419b-106">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="6419b-107">Si primero tiene que realizar una prueba con valores NULL y después probar el valor, resulta más cómodo realizar la consulta en una cláusula `let` y después utilizar los resultados en la cláusula `where`.</span><span class="sxs-lookup"><span data-stu-id="6419b-107">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6419b-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6419b-108">Example</span></span>  
 <span data-ttu-id="6419b-109">El siguiente ejemplo selecciona todos los elementos `p` que van seguidos inmediatamente por un elemento `ul`.</span><span class="sxs-lookup"><span data-stu-id="6419b-109">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```vb  
Dim doc As XElement = _  
    <Root>  
        <p id='1'/>  
        <ul>abc</ul>  
        <Child>  
            <p id='2'/>  
            <notul/>  
            <p id='3'/>  
            <ul>def</ul>  
            <p id='4'/>  
        </Child>  
        <Child>  
            <p id='5'/>  
            <notul/>  
            <p id='6'/>  
            <ul>abc</ul>  
            <p id='7'/>  
        </Child>  
    </Root>  
  
Dim items As IEnumerable(Of XElement) = _  
    From e In doc...<p> _  
    Let z = e.ElementsAfterSelf().FirstOrDefault() _  
    Where z IsNot Nothing AndAlso z.Name.LocalName = "ul" _  
    Select e  
  
For Each e As XElement In items  
    Console.WriteLine("id = {0}", e.@<id>)  
Next  
```  
  
 <span data-ttu-id="6419b-110">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6419b-110">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="6419b-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6419b-111">Example</span></span>  
 <span data-ttu-id="6419b-112">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6419b-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="6419b-113">Para obtener más información, consulte [trabajar con espacios de nombres XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="6419b-113">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim doc As XElement = _  
            <Root>  
                <p id='1'/>  
                <ul>abc</ul>  
                <Child>  
                    <p id='2'/>  
                    <notul/>  
                    <p id='3'/>  
                    <ul>def</ul>  
                    <p id='4'/>  
                </Child>  
                <Child>  
                    <p id='5'/>  
                    <notul/>  
                    <p id='6'/>  
                    <ul>abc</ul>  
                    <p id='7'/>  
                </Child>  
            </Root>  
  
        Dim items As IEnumerable(Of XElement) = _  
            From e In doc...<p> _  
            Let z = e.ElementsAfterSelf().FirstOrDefault() _  
            Where z IsNot Nothing AndAlso z.Name = GetXmlNamespace().GetName("ul") _  
            Select e  
  
        For Each e As XElement In items  
            Console.WriteLine("id = {0}", e.@<id>)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="6419b-114">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6419b-114">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="6419b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="6419b-115">See Also</span></span>  
 <xref:System.Xml.Linq.XElement.Parse%2A>  
 <xref:System.Xml.Linq.XContainer.Descendants%2A>  
 <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
 <xref:System.Linq.Enumerable.FirstOrDefault%2A>  
 [<span data-ttu-id="6419b-116">Consultas básicas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6419b-116">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
