---
title: Expresiones XPath compiladas
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: e25dd95f-b64c-4d8b-a3a4-379e1aa0ad55
ms.openlocfilehash: e74b52e471699fc663504fa42d6c7e502859adda
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291531"
---
# <a name="compiled-xpath-expressions"></a><span data-ttu-id="4d95e-102">Expresiones XPath compiladas</span><span class="sxs-lookup"><span data-stu-id="4d95e-102">Compiled XPath Expressions</span></span>
<span data-ttu-id="4d95e-103">Un objeto <xref:System.Xml.XPath.XPathExpression> representa una consulta XPath compilada devuelta desde el método <xref:System.Xml.XPath.XPathExpression.Compile%2A> estático de la clase <xref:System.Xml.XPath.XPathExpression> o desde el método <xref:System.Xml.XPath.XPathNavigator.Compile%2A> de la clase <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="4d95e-103">An <xref:System.Xml.XPath.XPathExpression> object represents a compiled XPath query returned from either the static <xref:System.Xml.XPath.XPathExpression.Compile%2A> method of the <xref:System.Xml.XPath.XPathExpression> class or the <xref:System.Xml.XPath.XPathNavigator.Compile%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
## <a name="the-xpathexpression-class"></a><span data-ttu-id="4d95e-104">La clase XPathExpression</span><span class="sxs-lookup"><span data-stu-id="4d95e-104">The XPathExpression Class</span></span>  
 <span data-ttu-id="4d95e-105">Una consulta XPath compilada que está representada por un objeto <xref:System.Xml.XPath.XPathExpression> es útil si esa misma consulta XPath se utiliza más de una vez.</span><span class="sxs-lookup"><span data-stu-id="4d95e-105">A compiled XPath query represented by an <xref:System.Xml.XPath.XPathExpression> object is useful if the same XPath query is being used more than once.</span></span>  
  
 <span data-ttu-id="4d95e-106">Por ejemplo, al llamar varias veces al método <xref:System.Xml.XPath.XPathNavigator.Select%2A>, en lugar de utilizar una cadena que represente a la consulta XPath cada una de esas veces, utilice el método <xref:System.Xml.XPath.XPathExpression.Compile%2A> de la clase <xref:System.Xml.XPath.XPathExpression> o el método <xref:System.Xml.XPath.XPathNavigator.Compile%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> para compilar y almacenar en caché la consulta XPath en un objeto <xref:System.Xml.XPath.XPathExpression>, para poder reutilizarla y mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4d95e-106">For example, when calling the <xref:System.Xml.XPath.XPathNavigator.Select%2A> method multiple times, instead of using a string representing the XPath query each time, use the <xref:System.Xml.XPath.XPathExpression.Compile%2A> method of the <xref:System.Xml.XPath.XPathExpression> class or the <xref:System.Xml.XPath.XPathNavigator.Compile%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class to compile and cache the XPath query in an <xref:System.Xml.XPath.XPathExpression> object for reuse and improved performance.</span></span>  
  
 <span data-ttu-id="4d95e-107">Una vez compilado, el objeto <xref:System.Xml.XPath.XPathExpression> se puede utilizar como entrada en los siguientes métodos de la clase <xref:System.Xml.XPath.XPathNavigator> dependiendo del tipo devuelto desde la consulta XPath.</span><span class="sxs-lookup"><span data-stu-id="4d95e-107">Once compiled, the <xref:System.Xml.XPath.XPathExpression> object may be used as input to the following <xref:System.Xml.XPath.XPathNavigator> class methods depending on the type returned from the XPath query.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.XPath.XPathNavigator.Matches%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
 <span data-ttu-id="4d95e-108">En la siguiente tabla se describe cada uno de los tipos de valores devueltos de XPath del W3C, sus equivalencias en Microsoft .NET Framework y con qué métodos se puede utilizar el objeto <xref:System.Xml.XPath.XPathExpression> basándose en su tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="4d95e-108">The following table describes each of the W3C XPath return types, their Microsoft .NET Framework equivalencies, and what methods the <xref:System.Xml.XPath.XPathExpression> object may be used with based on its return type.</span></span>  
  
|<span data-ttu-id="4d95e-109">Tipo de valor devuelto de XPath del W3C</span><span class="sxs-lookup"><span data-stu-id="4d95e-109">W3C XPath Return Type</span></span>|<span data-ttu-id="4d95e-110">Tipo equivalente en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4d95e-110">.NET Framework Equivalent Type</span></span>|<span data-ttu-id="4d95e-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d95e-111">Description</span></span>|<span data-ttu-id="4d95e-112">Métodos</span><span class="sxs-lookup"><span data-stu-id="4d95e-112">Methods</span></span>|  
|---------------------------|------------------------------------|-----------------|-------------|  
|`Node set`|<xref:System.Xml.XPath.XPathNodeIterator>|<span data-ttu-id="4d95e-113">Una colección no ordenada de nodos sin duplicados creados en el orden del documento.</span><span class="sxs-lookup"><span data-stu-id="4d95e-113">An unordered collection of nodes without duplicates created in document order.</span></span>|<span data-ttu-id="4d95e-114"><xref:System.Xml.XPath.XPathNavigator.Select%2A> o <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A></span><span class="sxs-lookup"><span data-stu-id="4d95e-114"><xref:System.Xml.XPath.XPathNavigator.Select%2A> or <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A></span></span>|  
|`Boolean`|<xref:System.Boolean>|<span data-ttu-id="4d95e-115">Un valor `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="4d95e-115">A `true` or `false` value.</span></span>|<span data-ttu-id="4d95e-116"><xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>, o bien</span><span class="sxs-lookup"><span data-stu-id="4d95e-116"><xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> or</span></span><br /><br /> <xref:System.Xml.XPath.XPathNavigator.Matches%2A>|  
|`Number`|<xref:System.Double>|<span data-ttu-id="4d95e-117">Número en punto flotante.</span><span class="sxs-lookup"><span data-stu-id="4d95e-117">A floating-point number.</span></span>|<xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>|  
|`String`|<xref:System.String>|<span data-ttu-id="4d95e-118">Una secuencia de caracteres UCS.</span><span class="sxs-lookup"><span data-stu-id="4d95e-118">A sequence of UCS characters.</span></span>|<xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>|  
  
> [!NOTE]
> <span data-ttu-id="4d95e-119">El método <xref:System.Xml.XPath.XPathNavigator.Matches%2A> acepta una expresión XPath como parámetro.</span><span class="sxs-lookup"><span data-stu-id="4d95e-119">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method accepts an XPath expression as its parameter.</span></span> <span data-ttu-id="4d95e-120">El método <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> devuelve un objeto <xref:System.Xml.XPath.XPathNavigator>, no uno de los tipos de valores devueltos de XPath del W3C.</span><span class="sxs-lookup"><span data-stu-id="4d95e-120">The <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> method returns an <xref:System.Xml.XPath.XPathNavigator> object, not one of the W3C XPath return types.</span></span>  
  
### <a name="the-returntype-property"></a><span data-ttu-id="4d95e-121">La propiedad ReturnType</span><span class="sxs-lookup"><span data-stu-id="4d95e-121">The ReturnType Property</span></span>  
 <span data-ttu-id="4d95e-122">Una vez compilada una consulta XPath en un objeto <xref:System.Xml.XPath.XPathExpression>, puede utilizar la propiedad <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> del objeto <xref:System.Xml.XPath.XPathExpression> para determinar qué devuelve la consulta XPath.</span><span class="sxs-lookup"><span data-stu-id="4d95e-122">After an XPath query has been compiled into an <xref:System.Xml.XPath.XPathExpression> object, you can use the <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> property of the <xref:System.Xml.XPath.XPathExpression> object to determine what the XPath query returns.</span></span>  
  
 <span data-ttu-id="4d95e-123">La propiedad <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> devuelve uno de los siguientes valores de enumeración <xref:System.Xml.XPath.XPathResultType> que representan los tipos de valores devueltos de XPath del W3C.</span><span class="sxs-lookup"><span data-stu-id="4d95e-123">The <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> property returns one of the following <xref:System.Xml.XPath.XPathResultType> enumeration values representing the W3C XPath return types.</span></span>  
  
- <xref:System.Xml.XPath.XPathResultType.Any>  
  
- <xref:System.Xml.XPath.XPathResultType.Boolean>  
  
- <xref:System.Xml.XPath.XPathResultType.Error>  
  
- <xref:System.Xml.XPath.XPathResultType.Navigator>  
  
- <xref:System.Xml.XPath.XPathResultType.NodeSet>  
  
- <xref:System.Xml.XPath.XPathResultType.Number>  
  
- <xref:System.Xml.XPath.XPathResultType.String>  
  
 <span data-ttu-id="4d95e-124">En el siguiente ejemplo se utiliza el objeto <xref:System.Xml.XPath.XPathExpression> para devolver un número y un conjunto de nodos desde el archivo `books.xml`.</span><span class="sxs-lookup"><span data-stu-id="4d95e-124">The following example uses the <xref:System.Xml.XPath.XPathExpression> object to return a number and a node set from the `books.xml` file.</span></span> <span data-ttu-id="4d95e-125">La propiedad <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> de cada objeto <xref:System.Xml.XPath.XPathExpression>, así como los resultados de los métodos <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> y <xref:System.Xml.XPath.XPathNavigator.Select%2A>, se escriben en la consola.</span><span class="sxs-lookup"><span data-stu-id="4d95e-125">The <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> property of each <xref:System.Xml.XPath.XPathExpression> object as well as the results from the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> and <xref:System.Xml.XPath.XPathNavigator.Select%2A> methods are written to the console.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Returns a number.  
Dim query1 As XPathExpression = navigator.Compile("bookstore/book/price/text()*10")  
Console.WriteLine(query1.ReturnType)  
  
Dim number As Double = CType(navigator.Evaluate(query1), Double)  
Console.WriteLine(number)  
  
' Returns a node set.  
Dim query2 As XPathExpression = navigator.Compile("bookstore/book/price")  
Console.WriteLine(query2.ReturnType)  
  
Dim nodes As XPathNodeIterator = navigator.Select(query2)  
nodes.MoveNext()  
Console.WriteLine(nodes.Current.Value)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Returns a number.  
XPathExpression query1 = navigator.Compile("bookstore/book/price/text()*10");  
Console.WriteLine(query1.ReturnType);  
  
Double number = (Double)navigator.Evaluate(query1);  
Console.WriteLine(number);  
  
// Returns a node set.  
XPathExpression query2 = navigator.Compile("bookstore/book/price");  
Console.WriteLine(query2.ReturnType);  
  
XPathNodeIterator nodes = navigator.Select(query2);  
nodes.MoveNext();  
Console.WriteLine(nodes.Current.Value);  
```  
  
 <span data-ttu-id="4d95e-126">En el ejemplo se toma como entrada el archivo `books.xml`.</span><span class="sxs-lookup"><span data-stu-id="4d95e-126">The example takes the `books.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="higher-performance-xpath-expressions"></a><span data-ttu-id="4d95e-127">Expresiones XPath de mayor rendimiento</span><span class="sxs-lookup"><span data-stu-id="4d95e-127">Higher Performance XPath Expressions</span></span>  
 <span data-ttu-id="4d95e-128">Para mejorar el rendimiento, utilice la expresión XPath lo más específica posible en las consultas.</span><span class="sxs-lookup"><span data-stu-id="4d95e-128">For better performance, use the most specific XPath expression possible in your queries.</span></span> <span data-ttu-id="4d95e-129">Por ejemplo, si el nodo `book` es un nodo secundario del nodo `bookstore` y el nodo `bookstore` es el elemento superior de un documento XML, es más rápido utilizar la expresión XPath `/bookstore/book` que `//book`.</span><span class="sxs-lookup"><span data-stu-id="4d95e-129">For example, if the `book` node is a child node of the `bookstore` node and the `bookstore` node is the top-most element in an XML document, using the XPath expression `/bookstore/book` is faster than using `//book`.</span></span> <span data-ttu-id="4d95e-130">La expresión XPath `//book` examinará cada nodo del árbol XML para identificar nodos coincidentes.</span><span class="sxs-lookup"><span data-stu-id="4d95e-130">The `//book` XPath expression will scan every node in the XML tree to identify matching nodes.</span></span>  
  
 <span data-ttu-id="4d95e-131">Además, el uso de métodos de navegación por conjuntos de nodos que proporciona la clase <xref:System.Xml.XPath.XPathNavigator>, puede producir una mejora del rendimiento con respecto a los métodos de selección que proporciona la clase <xref:System.Xml.XPath.XPathNavigator> en los casos en los que los criterios de selección sean sencillos.</span><span class="sxs-lookup"><span data-stu-id="4d95e-131">Additionally, using the node set navigation methods supplied by the <xref:System.Xml.XPath.XPathNavigator> class may result in improved performance over the selection methods supplied by the <xref:System.Xml.XPath.XPathNavigator> class in cases where your selection criteria are simple.</span></span> <span data-ttu-id="4d95e-132">Por ejemplo, si tiene que seleccionar el primer nodo secundario del nodo actual, es más rápido utilizar el método <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A> que la expresión XPath `child::*[1]` y el método <xref:System.Xml.XPath.XPathNavigator.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d95e-132">For example, if you need to select the first child of the current node, it is faster to use the <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A> method than to use the `child::*[1]` XPath expression and the <xref:System.Xml.XPath.XPathNavigator.Select%2A> method.</span></span>  
  
 <span data-ttu-id="4d95e-133">Para obtener más información sobre los métodos de navegación por conjuntos de nodos de la clase <xref:System.Xml.XPath.XPathNavigator>, vea [Navegación por un conjunto de nodos con XPathNavigator](node-set-navigation-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="4d95e-133">For more information about the node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class, see [Node Set Navigation Using XPathNavigator](node-set-navigation-using-xpathnavigator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d95e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d95e-134">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="4d95e-135">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="4d95e-135">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="4d95e-136">Seleccionar datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="4d95e-136">Select XML Data Using XPathNavigator</span></span>](select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="4d95e-137">Evaluación de expresiones XPath con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="4d95e-137">Evaluate XPath Expressions using XPathNavigator</span></span>](evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="4d95e-138">Coincidencia de nodos con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="4d95e-138">Matching Nodes using XPathNavigator</span></span>](matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="4d95e-139">Tipos de nodos reconocidos con consultas XPath</span><span class="sxs-lookup"><span data-stu-id="4d95e-139">Node Types Recognized with XPath Queries</span></span>](node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="4d95e-140">Espacios de nombres y consultas XPath</span><span class="sxs-lookup"><span data-stu-id="4d95e-140">XPath Queries and Namespaces</span></span>](xpath-queries-and-namespaces.md)
