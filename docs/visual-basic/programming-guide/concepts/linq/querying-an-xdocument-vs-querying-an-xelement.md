---
title: Diferencias entre realizar consultas de un XDocument y de un XElement
ms.date: 07/20/2015
ms.assetid: 2d111f84-0ded-4cde-8d93-5440557a726d
ms.openlocfilehash: 3cd79c8f2cde101de43a9b9e983709e2e0d11814
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396303"
---
# <a name="querying-an-xdocument-vs-querying-an-xelement-visual-basic"></a><span data-ttu-id="8d2d7-102">Consultar un XDocument y consultar un XElement (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d2d7-102">Querying an XDocument vs. Querying an XElement (Visual Basic)</span></span>
<span data-ttu-id="8d2d7-103">Cuando carga un documento mediante <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, observará que es necesario escribir las consultas de forma ligeramente diferente a como lo haría en caso de cargar el documento mediante <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8d2d7-103">When you load a document via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, you will notice that you have to write queries slightly differently than when you load via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a><span data-ttu-id="8d2d7-104">Comparación entre XDocument.Load y XElement.Load</span><span class="sxs-lookup"><span data-stu-id="8d2d7-104">Comparison of XDocument.Load and XElement.Load</span></span>  
 <span data-ttu-id="8d2d7-105">Cuando carga un documento XML en un <xref:System.Xml.Linq.XElement> mediante <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, el <xref:System.Xml.Linq.XElement> situado en la raíz del árbol XML contiene al elemento raíz del documento que se ha cargado.</span><span class="sxs-lookup"><span data-stu-id="8d2d7-105">When you load an XML document into an <xref:System.Xml.Linq.XElement> via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, the <xref:System.Xml.Linq.XElement> at the root of the XML tree contains the root element of the loaded document.</span></span> <span data-ttu-id="8d2d7-106">Sin embargo, cuando carga el mismo documento XML en un <xref:System.Xml.Linq.XDocument> mediante <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, la raíz del árbol es un nodo <xref:System.Xml.Linq.XDocument> el elemento raíz del documento cargado es el nodo secundario permitido <xref:System.Xml.Linq.XElement> de <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="8d2d7-106">However, when you load the same XML document into an <xref:System.Xml.Linq.XDocument> via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, the root of the tree is an <xref:System.Xml.Linq.XDocument> node, and the root element of the loaded document is the one allowed child <xref:System.Xml.Linq.XElement> node of the <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="8d2d7-107">Los ejes de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] funcionan en relación al nodo raíz.</span><span class="sxs-lookup"><span data-stu-id="8d2d7-107">The [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axes operate relative to the root node.</span></span>  
  
 <span data-ttu-id="8d2d7-108">Este primer ejemplo carga un árbol XML utilizando <xref:System.Xml.Linq.XElement.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="8d2d7-108">This first example loads an XML tree using <xref:System.Xml.Linq.XElement.Load%2A>.</span></span> <span data-ttu-id="8d2d7-109">A continuación, consulta los elementos secundarios de la raíz del árbol.</span><span class="sxs-lookup"><span data-stu-id="8d2d7-109">It then queries for the child elements of the root of the tree.</span></span>  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XElement.Load")  
Console.WriteLine("----")  
Dim doc As XElement = XElement.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="8d2d7-110">Como cabe esperar, este ejemplo genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8d2d7-110">As expected, this example produces the following output:</span></span>  
  
```console
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 <span data-ttu-id="8d2d7-111">El siguiente ejemplo es igual al anterior, con la diferencia de que el árbol XML se carga en un <xref:System.Xml.Linq.XDocument> en vez de un <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="8d2d7-111">The following example is the same as the one above, with the exception that the XML tree is loaded into an <xref:System.Xml.Linq.XDocument> instead of an <xref:System.Xml.Linq.XElement>.</span></span>  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="8d2d7-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8d2d7-112">This example produces the following output:</span></span>  
  
```console
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 <span data-ttu-id="8d2d7-113">Observe que la misma consulta devolvió el nodo `Root` en vez de los tres nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="8d2d7-113">Notice that the same query returned the one `Root` node instead of the three child nodes.</span></span>  
  
 <span data-ttu-id="8d2d7-114">Una forma de afrontar este asunto es utilizar la propiedad <xref:System.Xml.Linq.XDocument.Root%2A> antes de obtener acceso a los métodos de los ejes, tal y como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="8d2d7-114">One approach to dealing with this is to use the <xref:System.Xml.Linq.XDocument.Root%2A> property before accessing the axes methods, as follows:</span></span>  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Root.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="8d2d7-115">Ahora, esta consulta genera el mismo resultado que la consulta del árbol cuya raíz comienza en <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="8d2d7-115">This query now performs in the same way as the query on the tree rooted in <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="8d2d7-116">El ejemplo genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8d2d7-116">The example produces the following output:</span></span>  
  
```console
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d2d7-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d2d7-117">See also</span></span>

- [<span data-ttu-id="8d2d7-118">Consultas básicas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d2d7-118">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](basic-queries-linq-to-xml.md)
