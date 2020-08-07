---
title: Consultas compiladas estáticamente (LINQ to XML) (C#)
description: Aprenda sobre las consultas compiladas estáticamente en LINQ to XML en C# y el modo en que se diferencian de las consultas XPath, que deben interpretarse en tiempo de ejecución.
ms.date: 07/20/2015
ms.assetid: 3bf558fe-0705-479d-86d4-00188f5fcf9c
ms.openlocfilehash: cd2e6a6507311d5fc17215a22c70bd0449292b6f
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302313"
---
# <a name="statically-compiled-queries-linq-to-xml-c"></a><span data-ttu-id="cd69f-103">Consultas compiladas estáticamente (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="cd69f-103">Statically Compiled Queries (LINQ to XML) (C#)</span></span>
<span data-ttu-id="cd69f-104">Una de las ventajas de rendimiento más importantes de LINQ to XML, a diferencia de <xref:System.Xml.XmlDocument>, es que las consultas LINQ to XML se compilan estáticamente, mientras que las consultas XPath deben interpretarse durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="cd69f-104">One of the most important performance benefits LINQ to XML, as opposed to <xref:System.Xml.XmlDocument>, is that queries in LINQ to XML are statically compiled, whereas XPath queries must be interpreted at run time.</span></span> <span data-ttu-id="cd69f-105">Esta característica está incorporada en LINQ to XML, de modo que no tiene que efectuar pasos adicionales para aprovecharla, pero resulta útil comprender la distinción a la hora de elegir entre las dos tecnologías.</span><span class="sxs-lookup"><span data-stu-id="cd69f-105">This feature is built in to LINQ to XML, so you do not have to perform extra steps to take advantage of it, but it is helpful to understand the distinction when choosing between the two technologies.</span></span> <span data-ttu-id="cd69f-106">Este tema explica la diferencia.</span><span class="sxs-lookup"><span data-stu-id="cd69f-106">This topic explains the difference.</span></span>  
  
## <a name="statically-compiled-queries-vs-xpath"></a><span data-ttu-id="cd69f-107">Comparación de consultas compiladas de forma estática y XPath</span><span class="sxs-lookup"><span data-stu-id="cd69f-107">Statically Compiled Queries vs. XPath</span></span>  
 <span data-ttu-id="cd69f-108">En el ejemplo siguiente se muestra cómo obtener los elementos descendientes con un nombre especificado y con un atributo con un valor especificado.</span><span class="sxs-lookup"><span data-stu-id="cd69f-108">The following example shows how to get the descendant elements with a specified name, and with an attribute with a specified value.</span></span>  
  
 <span data-ttu-id="cd69f-109">Esta es la expresión XPath equivalente: `//Address[@Type='Shipping']`</span><span class="sxs-lookup"><span data-stu-id="cd69f-109">The following is the equivalent XPath expression: `//Address[@Type='Shipping']`</span></span>
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    from el in po.Descendants("Address")  
    where (string)el.Attribute("Type") == "Shipping"  
    select el;  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="cd69f-110">El compilador reescribe la expresión de consulta de este ejemplo con la sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="cd69f-110">The query expression in this example is re-written by the compiler to method-based query syntax.</span></span> <span data-ttu-id="cd69f-111">En el ejemplo siguiente, que está escrito en la sintaxis de consulta basada en métodos, se producen los mismos resultados que en el anterior:</span><span class="sxs-lookup"><span data-stu-id="cd69f-111">The following example, which is written in method-based query syntax, produces the same results as the previous one:</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    po  
    .Descendants("Address")  
    .Where(el => (string)el.Attribute("Type") == "Shipping");  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="cd69f-112">El método <xref:System.Linq.Enumerable.Where%2A> es una extensión del método.</span><span class="sxs-lookup"><span data-stu-id="cd69f-112">The <xref:System.Linq.Enumerable.Where%2A> method is an extension method.</span></span> <span data-ttu-id="cd69f-113">Para obtener más información, vea [Métodos de extensión](../../classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="cd69f-113">For more information, see [Extension Methods](../../classes-and-structs/extension-methods.md).</span></span> <span data-ttu-id="cd69f-114">Dado que <xref:System.Linq.Enumerable.Where%2A> es un método de extensión, la consulta anterior se compila como si estuviera escrita como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="cd69f-114">Because <xref:System.Linq.Enumerable.Where%2A> is an extension method, the query above is compiled as though it were written as follows:</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    System.Linq.Enumerable.Where(  
        po.Descendants("Address"),  
        el => (string)el.Attribute("Type") == "Shipping");  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="cd69f-115">Este ejemplo produce exactamente los mismos resultados que los dos ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="cd69f-115">This example produces exactly the same results as the previous two examples.</span></span> <span data-ttu-id="cd69f-116">Esto ilustra el hecho de que las consultas se compilan de forma efectiva en llamadas a método vinculadas estáticamente.</span><span class="sxs-lookup"><span data-stu-id="cd69f-116">This illustrates the fact that queries are effectively compiled into statically linked method calls.</span></span> <span data-ttu-id="cd69f-117">Esto, combinado con la semántica de ejecución aplazada de los iteradores, mejora el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="cd69f-117">This, combined with the deferred execution semantics of iterators, improves performance.</span></span> <span data-ttu-id="cd69f-118">Para obtener más información sobre la semántica de ejecución aplazada de iteradores, vea [Ejecución aplazada y evaluación diferida en LINQ to XML](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="cd69f-118">For more information about the deferred execution semantics of iterators, see [Deferred Execution and Lazy Evaluation in LINQ to XML (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd69f-119">Estos ejemplos son representativos del código que el compilador podría escribir.</span><span class="sxs-lookup"><span data-stu-id="cd69f-119">These examples are representative of the code that the compiler might write.</span></span> <span data-ttu-id="cd69f-120">La implementación real podría diferir ligeramente de estos ejemplos, pero el rendimiento será el mismo o similar a estos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="cd69f-120">The actual implementation might differ slightly from these examples, but the performance will be the same or similar to these examples.</span></span>  
  
## <a name="executing-xpath-expressions-with-xmldocument"></a><span data-ttu-id="cd69f-121">Ejecutar expresiones XPath con XmlDocument</span><span class="sxs-lookup"><span data-stu-id="cd69f-121">Executing XPath Expressions with XmlDocument</span></span>  
 <span data-ttu-id="cd69f-122">En el ejemplo de código siguiente se usa <xref:System.Xml.XmlDocument> para lograr los mismos resultados que en los ejemplos anteriores:</span><span class="sxs-lookup"><span data-stu-id="cd69f-122">The following example uses <xref:System.Xml.XmlDocument> to accomplish the same results as the previous examples:</span></span>  
  
```csharp  
XmlReader reader = XmlReader.Create("PurchaseOrders.xml");  
XmlDocument doc = new XmlDocument();  
doc.Load(reader);  
XmlNodeList nl = doc.SelectNodes(".//Address[@Type='Shipping']");  
foreach (XmlNode n in nl)  
    Console.WriteLine(n.OuterXml);  
reader.Close();  
```  
  
 <span data-ttu-id="cd69f-123">Esta consulta devuelve el mismo resultado que los ejemplos que usan LINQ to XML; la única diferencia es que LINQ to XML aplica sangría al XML impreso, mientras que <xref:System.Xml.XmlDocument> no.</span><span class="sxs-lookup"><span data-stu-id="cd69f-123">This query returns the same output as the examples that use LINQ to XML; the only difference is that LINQ to XML indents the printed XML, whereas <xref:System.Xml.XmlDocument> does not.</span></span>  
  
 <span data-ttu-id="cd69f-124">No obstante, el enfoque de <xref:System.Xml.XmlDocument> generalmente no funciona tan bien como LINQ to XML, porque el método <xref:System.Xml.XmlNode.SelectNodes%2A> debe realizar lo siguiente internamente cada vez que se le llama:</span><span class="sxs-lookup"><span data-stu-id="cd69f-124">However, the <xref:System.Xml.XmlDocument> approach generally does not perform as well as LINQ to XML, because the <xref:System.Xml.XmlNode.SelectNodes%2A> method must do the following internally every time it is called:</span></span>  
  
- <span data-ttu-id="cd69f-125">Analiza la cadena que contiene la expresión XPath, y divide la cadena en tokens.</span><span class="sxs-lookup"><span data-stu-id="cd69f-125">It parses the string that contains the XPath expression, breaking the string into tokens.</span></span>  
  
- <span data-ttu-id="cd69f-126">Valida los tokens para asegurarse de que la expresión XPath es válida.</span><span class="sxs-lookup"><span data-stu-id="cd69f-126">It validates the tokens to make sure that the XPath expression is valid.</span></span>  
  
- <span data-ttu-id="cd69f-127">Traduce la expresión a un árbol de expresión interno.</span><span class="sxs-lookup"><span data-stu-id="cd69f-127">It translates the expression into an internal expression tree.</span></span>  
  
- <span data-ttu-id="cd69f-128">Recorre en iteración los nodos, y selecciona de forma adecuada los nodos del conjunto de resultados basándose en la evaluación de la expresión.</span><span class="sxs-lookup"><span data-stu-id="cd69f-128">It iterates through the nodes, appropriately selecting the nodes for the result set based on the evaluation of the expression.</span></span>  
  
 <span data-ttu-id="cd69f-129">Esto es bastante más que el trabajo realizado por la consulta LINQ to XML correspondiente.</span><span class="sxs-lookup"><span data-stu-id="cd69f-129">This is significantly more than the work done by the corresponding LINQ to XML query.</span></span> <span data-ttu-id="cd69f-130">La diferencia de rendimiento específica varía para distintos tipos de consultas, pero en general las consultas LINQ to XML efectúan menos operaciones y, por lo tanto, se ejecutan mejor, que si se evalúan las expresiones XPath con <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="cd69f-130">The specific performance difference varies for different types of queries, but in general LINQ to XML queries do less work, and therefore perform better, than evaluating XPath expressions using <xref:System.Xml.XmlDocument>.</span></span>  
