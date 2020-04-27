---
title: Selección de nodos con la navegación XPath
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 8e4450dc-56b3-472b-b467-32f5694f83ad
ms.openlocfilehash: 58f1487486c2802a2c64b51afcecb01c76dd291a
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155612"
---
# <a name="select-nodes-using-xpath-navigation"></a><span data-ttu-id="26282-102">Selección de nodos con la navegación XPath</span><span class="sxs-lookup"><span data-stu-id="26282-102">Select Nodes Using XPath Navigation</span></span>
<span data-ttu-id="26282-103">El Modelo de objetos del documento (DOM) XML contiene métodos que le permiten utilizar la navegación del lenguaje de ruta XML (XPath) para consultar información en el DOM.</span><span class="sxs-lookup"><span data-stu-id="26282-103">The XML Document Object Model (DOM) contains methods that allow you to use XML Path Language (XPath) navigation to query information in the DOM.</span></span> <span data-ttu-id="26282-104">Puede utilizar XPath para buscar un solo nodo específico o para buscar todos los nodos que cumplen algunos criterios.</span><span class="sxs-lookup"><span data-stu-id="26282-104">You can use XPath to find a single, specific node or to find all nodes that match some criteria.</span></span>  
  
## <a name="xpath-select-methods"></a><span data-ttu-id="26282-105">Métodos de selección de XPath</span><span class="sxs-lookup"><span data-stu-id="26282-105">XPath Select Methods</span></span>  
 <span data-ttu-id="26282-106">Las clases DOM incluyen dos métodos para la selección de XPath: <xref:System.Xml.XmlNode.SelectSingleNode%2A> y <xref:System.Xml.XmlNode.SelectNodes%2A>.</span><span class="sxs-lookup"><span data-stu-id="26282-106">The DOM classes provide two methods for XPath selection: the <xref:System.Xml.XmlNode.SelectSingleNode%2A> method and the <xref:System.Xml.XmlNode.SelectNodes%2A> method.</span></span> <span data-ttu-id="26282-107">El método <xref:System.Xml.XmlNode.SelectSingleNode%2A> devuelve el primer nodo que cumple los criterios de selección.</span><span class="sxs-lookup"><span data-stu-id="26282-107">The <xref:System.Xml.XmlNode.SelectSingleNode%2A> method returns the first node that matches the selection criteria.</span></span> <span data-ttu-id="26282-108">El método <xref:System.Xml.XmlNode.SelectNodes%2A> devuelve un <xref:System.Xml.XmlNodeList> que contiene los nodos coincidentes.</span><span class="sxs-lookup"><span data-stu-id="26282-108">The <xref:System.Xml.XmlNode.SelectNodes%2A> method returns an <xref:System.Xml.XmlNodeList> that contains the matching nodes.</span></span>  
  
 <span data-ttu-id="26282-109">En el siguiente ejemplo se utiliza el método <xref:System.Xml.XmlNode.SelectSingleNode%2A> para seleccionar el primer nodo `book` en el que el apellido del autor cumple los criterios especificados.</span><span class="sxs-lookup"><span data-stu-id="26282-109">The following example uses the <xref:System.Xml.XmlNode.SelectSingleNode%2A> method to select the first `book` node in which the author's last name meets the specified criteria.</span></span> <span data-ttu-id="26282-110">El archivo bookstore.xml (que se proporciona al final de este tema) se utiliza como archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="26282-110">The bookstore.xml file (which is provided at the end of this topic) is used as the input file.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
doc.Load("bookstore.xml")  
Dim root As XmlNode = doc.DocumentElement  
  
' Add the namespace.  
Dim nsmgr As New XmlNamespaceManager(doc.NameTable)  
nsmgr.AddNamespace("bk", "urn:newbooks-schema")  
  
' Select and display the first node in which the author's
' last name is Kingsolver.  
Dim node As XmlNode = root.SelectSingleNode( _  
     "descendant::bk:book[bk:author/bk:last-name='Kingsolver']", nsmgr)  
Console.WriteLine(node.InnerXml)  
```  
  
```csharp  
// Load the document and set the root element.  
XmlDocument doc = new XmlDocument();  
doc.Load("bookstore.xml");  
XmlNode root = doc.DocumentElement;  
  
// Add the namespace.  
XmlNamespaceManager nsmgr = new XmlNamespaceManager(doc.NameTable);  
nsmgr.AddNamespace("bk", "urn:newbooks-schema");  
  
// Select and display the first node in which the author's
// last name is Kingsolver.  
XmlNode node = root.SelectSingleNode(  
    "descendant::bk:book[bk:author/bk:last-name='Kingsolver']", nsmgr);  
Console.WriteLine(node.InnerXml);  
```  
  
 <span data-ttu-id="26282-111">En el ejemplo siguiente, el método <xref:System.Xml.XmlNode.SelectNodes%2A> se utiliza para seleccionar todos los nodos de libro cuyo precio es mayor que una cantidad dada.</span><span class="sxs-lookup"><span data-stu-id="26282-111">The next example uses the <xref:System.Xml.XmlNode.SelectNodes%2A> method to select all the book nodes in which the price is greater than a specified amount.</span></span> <span data-ttu-id="26282-112">A continuación, el precio de cada libro de la lista seleccionada se reduce en un diez por ciento mediante programación.</span><span class="sxs-lookup"><span data-stu-id="26282-112">The price for each book in the selected list is then programmatically reduced by ten percent.</span></span> <span data-ttu-id="26282-113">Por último, el archivo actualizado se escribe en la consola.</span><span class="sxs-lookup"><span data-stu-id="26282-113">Finally, the updated file is written to the console.</span></span> <span data-ttu-id="26282-114">El archivo bookstore.xml (que se proporciona al final de este tema) se utiliza como archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="26282-114">The bookstore.xml file (which is provided at the end of this topic) is used as the input file.</span></span>  
  
```vb  
' Load the document and set the root element.  
Dim doc As New XmlDocument()  
doc.Load("bookstore.xml")  
Dim root As XmlNode = doc.DocumentElement  
  
' Add the namespace.  
Dim nsmgr As New XmlNamespaceManager(doc.NameTable)  
nsmgr.AddNamespace("bk", "urn:newbooks-schema")  
  
' Select all nodes where the book price is greater than 10.00.  
Dim nodeList As XmlNodeList = root.SelectNodes( _  
     "descendant::bk:book[bk:price>10.00]", nsmgr)  
For Each book As XmlNode In nodeList  
     Dim price As Double  
     price = Math.Round(Convert.ToSingle( _  
          book.LastChild.InnerText) * 0.9, 2)  
     book.LastChild.InnerText = price.ToString()  
Next  
  
' Display the updated document.  
doc.Save(Console.Out)  
```  
  
```csharp  
// Load the document and set the root element.  
XmlDocument doc = new XmlDocument();  
doc.Load("bookstore.xml");  
XmlNode root = doc.DocumentElement;  
  
// Add the namespace.  
XmlNamespaceManager nsmgr = new XmlNamespaceManager(doc.NameTable);  
nsmgr.AddNamespace("bk", "urn:newbooks-schema");  
  
// Select all nodes where the book price is greater than 10.00.  
XmlNodeList nodeList = root.SelectNodes(  
     "descendant::bk:book[bk:price>10.00]", nsmgr);  
foreach (XmlNode book in nodeList)  
{  
     // Discount prices by 10%.  
     double price;  
     price = Math.Round(Convert.ToSingle(  
          book.LastChild.InnerText) * 0.9, 2);  
     book.LastChild.InnerText = price.ToString();  
}  
  
// Display the updated document.  
doc.Save(Console.Out);  
```  
  
 <span data-ttu-id="26282-115">Los ejemplos anteriores comienzan la consulta XPath en el elemento de documento.</span><span class="sxs-lookup"><span data-stu-id="26282-115">The examples above start the XPath query at the document element.</span></span> <span data-ttu-id="26282-116">Al establecer el punto de inicio de la consulta XPath, se establece el nodo de contexto, que es el punto de inicio de la consulta XPath.</span><span class="sxs-lookup"><span data-stu-id="26282-116">Setting the starting point for the XPath query sets the context node, which is the starting point for the XPath query.</span></span> <span data-ttu-id="26282-117">Si no desea comenzar en el elemento de documento, sino en el primer elemento secundario del elemento de documento, puede codificar la instrucción SELECT como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="26282-117">If you do not want to start at the document element, but want to start from the first child of the document element, you can code the select statement as follows:</span></span>  
  
```vb  
doc.DocumentElement.FirstChild.SelectNodes(. . . )  
```  
  
```csharp  
this doc.DocumentElement.FirstChild.SelectNodes(. . .);  
```  
  
 <span data-ttu-id="26282-118">Todos los objetos <xref:System.Xml.XmlNodeList> se sincronizan con el documento subyacente.</span><span class="sxs-lookup"><span data-stu-id="26282-118">All <xref:System.Xml.XmlNodeList> objects are synchronized with the underlying document.</span></span> <span data-ttu-id="26282-119">Por lo tanto, si itera a través de la lista de nodos y modifica el valor de un nodo, ese nodo también se actualiza en el documento del que proviene.</span><span class="sxs-lookup"><span data-stu-id="26282-119">Therefore, if you iterate through the node list and modify the value of a node, that node is also updated in the document it came from.</span></span> <span data-ttu-id="26282-120">En el ejemplo anterior observe que cuando se modifica un nodo en el objeto <xref:System.Xml.XmlNodeList> seleccionado, se modifica también el documento subyacente.</span><span class="sxs-lookup"><span data-stu-id="26282-120">Notice in the previous example that when a node is modified in the selected <xref:System.Xml.XmlNodeList> the underlying document is also modified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26282-121">Cuando se modifica el documento subyacente, es aconsejable volver a ejecutar la selección.</span><span class="sxs-lookup"><span data-stu-id="26282-121">When the underlying document is modified, it is advisable to rerun the select.</span></span> <span data-ttu-id="26282-122">Si el nodo modificado puede provocar que el nodo se agregue a la lista de nodos cuando antes no estaba, o que se quite de la lista de nodos, no hay ninguna garantía de que la lista de nodos sea precisa.</span><span class="sxs-lookup"><span data-stu-id="26282-122">If the node modified is one that could cause the node to be added to the node list when it was not previously, or would now cause it to be removed from the node list, there is no guarantee that the node list is now accurate.</span></span>  
  
## <a name="namespaces-in-xpath-expressions"></a><span data-ttu-id="26282-123">Espacios de nombres en expresiones XPath</span><span class="sxs-lookup"><span data-stu-id="26282-123">Namespaces in XPath Expressions</span></span>  
 <span data-ttu-id="26282-124">Las expresiones XPath pueden incluir espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="26282-124">XPath expressions can include namespaces.</span></span> <span data-ttu-id="26282-125">La resolución de espacios de nombres es compatible con <xref:System.Xml.XmlNamespaceManager>.</span><span class="sxs-lookup"><span data-stu-id="26282-125">Namespace resolution is supported using the <xref:System.Xml.XmlNamespaceManager>.</span></span> <span data-ttu-id="26282-126">Si la expresión XPath incluye un prefijo, el par del prefijo y el identificador URI de espacio de nombres se debe agregar a <xref:System.Xml.XmlNamespaceManager>, y <xref:System.Xml.XmlNamespaceManager> se pasa al método <xref:System.Xml.XmlNode.SelectNodes%28System.String%2CSystem.Xml.XmlNamespaceManager%29> o <xref:System.Xml.XmlNode.SelectSingleNode%28System.String%2CSystem.Xml.XmlNamespaceManager%29>.</span><span class="sxs-lookup"><span data-stu-id="26282-126">If the XPath expression includes a prefix, the prefix and namespace URI pair must be added to the <xref:System.Xml.XmlNamespaceManager>, and the <xref:System.Xml.XmlNamespaceManager> is passed to the <xref:System.Xml.XmlNode.SelectNodes%28System.String%2CSystem.Xml.XmlNamespaceManager%29> or <xref:System.Xml.XmlNode.SelectSingleNode%28System.String%2CSystem.Xml.XmlNamespaceManager%29> method.</span></span> <span data-ttu-id="26282-127">Observe que los ejemplos de código anteriores utilizan <xref:System.Xml.XmlNamespaceManager> para resolver el espacio de nombres del documento bookstore.xml.</span><span class="sxs-lookup"><span data-stu-id="26282-127">Notice that the code examples above use the <xref:System.Xml.XmlNamespaceManager> to resolve the namespace of the bookstore.xml document.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26282-128">Si la expresión XPath no incluye un prefijo, se asume que el identificador uniforme de recursos (URI) de espacio de nombres es el espacio de nombres vacío.</span><span class="sxs-lookup"><span data-stu-id="26282-128">If the XPath expression does not include a prefix, it is assumed that the namespace Uniform Resource Identifier (URI) is the empty namespace.</span></span> <span data-ttu-id="26282-129">Si el XML incluye un espacio de nombres predeterminado, deberá agregar también un prefijo y un identificador URI de espacio de nombres a <xref:System.Xml.XmlNamespaceManager>; de lo contrario, no se seleccionará ningún nodo.</span><span class="sxs-lookup"><span data-stu-id="26282-129">If your XML includes a default namespace, you must still add a prefix and namespace URI to the <xref:System.Xml.XmlNamespaceManager>; otherwise, no nodes will be selected.</span></span>  
  
#### <a name="input-file"></a><span data-ttu-id="26282-130">Archivo de entrada</span><span class="sxs-lookup"><span data-stu-id="26282-130">Input File</span></span>  
 <span data-ttu-id="26282-131">A continuación, se muestra el archivo bookstore.xml que se utiliza como archivo de entrada en los ejemplos incluidos en este tema:</span><span class="sxs-lookup"><span data-stu-id="26282-131">The following is the bookstore.xml file that is used as the input file in the examples in this topic:</span></span>  
  
```xml  
<?xml version='1.0'?>  
<bookstore xmlns="urn:newbooks-schema">  
  <book genre="novel" style="hardcover">  
    <title>The Handmaid's Tale</title>  
    <author>  
      <first-name>Margaret</first-name>  
      <last-name>Atwood</last-name>  
    </author>  
    <price>19.95</price>  
  </book>  
  <book genre="novel" style="other">  
    <title>The Poisonwood Bible</title>  
    <author>  
      <first-name>Barbara</first-name>  
      <last-name>Kingsolver</last-name>  
    </author>  
    <price>11.99</price>  
  </book>  
  <book genre="novel" style="paperback">  
    <title>The Bean Trees</title>  
    <author>  
      <first-name>Barbara</first-name>  
      <last-name>Kingsolver</last-name>  
    </author>  
    <price>5.99</price>  
  </book>  
</bookstore>  
```  
  
## <a name="see-also"></a><span data-ttu-id="26282-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="26282-132">See also</span></span>

- [<span data-ttu-id="26282-133">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="26282-133">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
