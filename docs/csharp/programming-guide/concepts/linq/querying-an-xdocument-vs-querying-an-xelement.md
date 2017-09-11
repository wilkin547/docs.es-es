---
title: Diferencias entre realizar consultas de un XDocument Realizar consultas de un XElement (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 46221ff5-62ee-4de8-93ba-66465facb5c1
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fa756d4adb1c361ef52e58bf6bdfd3bc2e31d13a
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="querying-an-xdocument-vs-querying-an-xelement-c"></a><span data-ttu-id="8788b-102">Diferencias entre realizar consultas de un XDocument Realizar consultas de un XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="8788b-102">Querying an XDocument vs. Querying an XElement (C#)</span></span>
<span data-ttu-id="8788b-103">Cuando carga un documento mediante <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, observará que es necesario escribir las consultas de forma ligeramente diferente a como lo haría en caso de cargar el documento mediante <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="8788b-103">When you load a document via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, you will notice that you have to write queries slightly differently than when you load via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>.</span></span>  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a><span data-ttu-id="8788b-104">Comparación entre XDocument.Load y XElement.Load</span><span class="sxs-lookup"><span data-stu-id="8788b-104">Comparison of XDocument.Load and XElement.Load</span></span>  
 <span data-ttu-id="8788b-105">Cuando carga un documento XML en un <xref:System.Xml.Linq.XElement> mediante <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, el <xref:System.Xml.Linq.XElement> situado en la raíz del árbol XML contiene al elemento raíz del documento que se ha cargado.</span><span class="sxs-lookup"><span data-stu-id="8788b-105">When you load an XML document into an <xref:System.Xml.Linq.XElement> via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, the <xref:System.Xml.Linq.XElement> at the root of the XML tree contains the root element of the loaded document.</span></span> <span data-ttu-id="8788b-106">Sin embargo, cuando carga el mismo documento XML en un <xref:System.Xml.Linq.XDocument> mediante <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, la raíz del árbol es un nodo <xref:System.Xml.Linq.XDocument> el elemento raíz del documento cargado es el nodo secundario permitido <xref:System.Xml.Linq.XElement> de <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="8788b-106">However, when you load the same XML document into an <xref:System.Xml.Linq.XDocument> via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, the root of the tree is an <xref:System.Xml.Linq.XDocument> node, and the root element of the loaded document is the one allowed child <xref:System.Xml.Linq.XElement> node of the <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="8788b-107">Los ejes de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] funcionan en relación al nodo raíz.</span><span class="sxs-lookup"><span data-stu-id="8788b-107">The [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axes operate relative to the root node.</span></span>  
  
 <span data-ttu-id="8788b-108">Este primer ejemplo carga un árbol XML utilizando <xref:System.Xml.Linq.XElement.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="8788b-108">This first example loads an XML tree using <xref:System.Xml.Linq.XElement.Load%2A>.</span></span> <span data-ttu-id="8788b-109">A continuación, consulta los elementos secundarios de la raíz del árbol.</span><span class="sxs-lookup"><span data-stu-id="8788b-109">It then queries for the child elements of the root of the tree.</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XElement.Load");  
Console.WriteLine("----");  
XElement doc = XElement.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="8788b-110">Como cabe esperar, este ejemplo genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8788b-110">As expected, this example produces the following output:</span></span>  
  
```  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 <span data-ttu-id="8788b-111">El siguiente ejemplo es igual al anterior, con la diferencia de que el árbol XML se carga en un <xref:System.Xml.Linq.XDocument> en vez de un <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="8788b-111">The following example is the same as the one above, with the exception that the XML tree is loaded into an <xref:System.Xml.Linq.XDocument> instead of an <xref:System.Xml.Linq.XElement>.</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="8788b-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8788b-112">This example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 <span data-ttu-id="8788b-113">Observe que la misma consulta devolvió el nodo `Root` en vez de los tres nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="8788b-113">Notice that the same query returned the one `Root` node instead of the three child nodes.</span></span>  
  
 <span data-ttu-id="8788b-114">Una forma de afrontar este asunto es utilizar la propiedad <xref:System.Xml.Linq.XDocument.Root%2A> antes de obtener acceso a los métodos de los ejes, tal y como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="8788b-114">One approach to dealing with this is to use the <xref:System.Xml.Linq.XDocument.Root%2A> property before accessing the axes methods, as follows:</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Root.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="8788b-115">Ahora, esta consulta genera el mismo resultado que la consulta del árbol cuya raíz comienza en <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="8788b-115">This query now performs in the same way as the query on the tree rooted in <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="8788b-116">El ejemplo genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8788b-116">The example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8788b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="8788b-117">See Also</span></span>  
 [<span data-ttu-id="8788b-118">Consultas básicas (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="8788b-118">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)

