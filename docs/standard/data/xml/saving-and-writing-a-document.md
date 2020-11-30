---
title: Guardar y escribir un documento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 097b0cb1-5743-4c3a-86ef-caf5cbe6750d
ms.openlocfilehash: 14497bb5b027209c4707eab9bcf1b60f85740dfd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697563"
---
# <a name="saving-and-writing-a-document"></a><span data-ttu-id="c2fd0-102">Guardar y escribir un documento</span><span class="sxs-lookup"><span data-stu-id="c2fd0-102">Saving and Writing a Document</span></span>

<span data-ttu-id="c2fd0-103">Cuando cargue y guarde un <xref:System.Xml.XmlDocument>, el documento guardado puede ser diferente al original de varias formas:</span><span class="sxs-lookup"><span data-stu-id="c2fd0-103">When you load and save an <xref:System.Xml.XmlDocument>, the saved document may differ from the original in the following ways:</span></span>  
  
- <span data-ttu-id="c2fd0-104">Si la propiedad <xref:System.Xml.XmlDocument.PreserveWhitespace%2A> se establece en `true` antes de llamar al método <xref:System.Xml.XmlDocument.Save%2A>, en el resultado se conserva el espacio en blanco del documento; sin embargo, si la propiedad es `false`, <xref:System.Xml.XmlDocument>, se aplica sangría automáticamente al resultado.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-104">If the <xref:System.Xml.XmlDocument.PreserveWhitespace%2A> property is set to `true` before the <xref:System.Xml.XmlDocument.Save%2A> method is called, white space in the document is preserved in the output; if this property is `false`, <xref:System.Xml.XmlDocument> auto-indents the output.</span></span>  
  
- <span data-ttu-id="c2fd0-105">Todos los espacios en blanco entre los atributos se reducen a un carácter de un solo espacio.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-105">All the white space between attributes is reduced to a single space character.</span></span>  
  
- <span data-ttu-id="c2fd0-106">Se cambia el espacio en blanco entre los elementos.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-106">The white space between elements is changed.</span></span> <span data-ttu-id="c2fd0-107">Se conserva el espacio blanco importante, pero no se conserva el poco importante.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-107">Significant white space is preserved and insignificant white space is not.</span></span> <span data-ttu-id="c2fd0-108">No obstante, cuando se guarda el documento, se usa el modo <xref:System.Xml.XmlTextWriter> **Sangría** de manera predeterminada para imprimir con claridad el resultado con el fin de que sea más legible.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-108">But when the document is saved, it will use the <xref:System.Xml.XmlTextWriter> **Indenting** mode by default to neatly print the output to make it more readable.</span></span>  
  
- <span data-ttu-id="c2fd0-109">De manera predeterminada, el carácter de la comilla que se utiliza delante y detrás de los valores de los atributos se cambia por la comilla doble.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-109">The quote character used around attribute values is changed to double quote by default.</span></span> <span data-ttu-id="c2fd0-110">Puede utilizar la propiedad <xref:System.Xml.XmlTextReader.QuoteChar%2A> en <xref:System.Xml.XmlTextWriter>para establecer el carácter de la comilla como doble o simple.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-110">You can use the <xref:System.Xml.XmlTextReader.QuoteChar%2A> property on <xref:System.Xml.XmlTextWriter> to set the quote character to either double quote or single quote.</span></span>  
  
- <span data-ttu-id="c2fd0-111">De manera predeterminada, se expanden las entidades de caracteres numéricos como `{`.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-111">By default, numeric character entities like `{` are expanded.</span></span>  
  
- <span data-ttu-id="c2fd0-112">No se conserva la marca de orden de bytes del documento de entrada.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-112">The byte-order mark found in the input document is not preserved.</span></span> <span data-ttu-id="c2fd0-113">UCS-2 se guarda como UTF-8 a menos que cree explícitamente una declaración XML en la que se especifique otra codificación.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-113">UCS-2 is saved as UTF-8 unless you explicitly create an XML declaration that specifies a different encoding.</span></span>  
  
- <span data-ttu-id="c2fd0-114">Si desea escribir <xref:System.Xml.XmlDocument> en un archivo o una secuencia, el resultado escrito es el mismo que el contenido del documento.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-114">If you want to write out the <xref:System.Xml.XmlDocument> into a file or stream, the output written out is the same as the content of the document.</span></span> <span data-ttu-id="c2fd0-115">Es decir, la declaración <xref:System.Xml.XmlDeclaration> solo se escribe si hay alguna en el documento y la codificación que se utiliza al escribir el documento es la misma que la del nodo de la declaración.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-115">That is, the <xref:System.Xml.XmlDeclaration> is written out only if there is one contained in the document, and the encoding used when writing out the document is the same encoding given in the declaration node.</span></span>  
  
## <a name="writing-an-xmldeclaration"></a><span data-ttu-id="c2fd0-116">Escribir una declaración XmlDeclaration</span><span class="sxs-lookup"><span data-stu-id="c2fd0-116">Writing an XmlDeclaration</span></span>  

 <span data-ttu-id="c2fd0-117">Los miembros <xref:System.Xml.XmlDocument> y <xref:System.Xml.XmlDeclaration> de <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlNode.InnerXml%2A> y <xref:System.Xml.XmlNode.WriteTo%2A>, además de los métodos <xref:System.Xml.XmlDocument> de <xref:System.Xml.XmlDocument.Save%2A> y <xref:System.Xml.XmlDocument.WriteContentTo%2A>, crean una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-117">The <xref:System.Xml.XmlDocument> and <xref:System.Xml.XmlDeclaration> members of <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlNode.InnerXml%2A>, and <xref:System.Xml.XmlNode.WriteTo%2A>, in addition to the <xref:System.Xml.XmlDocument> methods of <xref:System.Xml.XmlDocument.Save%2A> and <xref:System.Xml.XmlDocument.WriteContentTo%2A>, create an XML declaration.</span></span>  
  
 <span data-ttu-id="c2fd0-118">Para las propiedades <xref:System.Xml.XmlDocument> de <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlDocument.InnerXml%2A>, y los métodos <xref:System.Xml.XmlDocument.Save%2A>, <xref:System.Xml.XmlDocument.WriteTo%2A> y <xref:System.Xml.XmlDocument.WriteContentTo%2A>, la codificación escrita en la declaración XML se obtiene del nodo <xref:System.Xml.XmlDeclaration>.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-118">For the <xref:System.Xml.XmlDocument> properties of <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlDocument.InnerXml%2A>, and the <xref:System.Xml.XmlDocument.Save%2A>, <xref:System.Xml.XmlDocument.WriteTo%2A>, and <xref:System.Xml.XmlDocument.WriteContentTo%2A> methods, the encoding written out in the XML declaration is taken from the <xref:System.Xml.XmlDeclaration> node.</span></span> <span data-ttu-id="c2fd0-119">Si no existe ningún nodo <xref:System.Xml.XmlDeclaration>, <xref:System.Xml.XmlDeclaration> no se escribe. Si no hay codificación en el nodo <xref:System.Xml.XmlDeclaration>, la codificación no se escribe en la declaración XML.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-119">If there is no <xref:System.Xml.XmlDeclaration> node, <xref:System.Xml.XmlDeclaration> is not written out. If there is no encoding in the <xref:System.Xml.XmlDeclaration> node, encoding is not written out in the XML declaration.</span></span>  
  
 <span data-ttu-id="c2fd0-120">Los métodos <xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType> y <xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType> siempre escriben una declaración <xref:System.Xml.XmlDeclaration>.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-120">The <xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType> and <xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType> methods always write out an <xref:System.Xml.XmlDeclaration>.</span></span> <span data-ttu-id="c2fd0-121">Estos métodos toman la codificación del sistema de escritura que está escribiendo.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-121">These methods take the encoding from the writer that it is writing to.</span></span> <span data-ttu-id="c2fd0-122">Es decir, el valor de codificación en el sistema de escritura invalida la codificación en el documento y en la declaración <xref:System.Xml.XmlDeclaration>.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-122">That is, the encoding value on the writer overrides the encoding on the document and in the <xref:System.Xml.XmlDeclaration>.</span></span> <span data-ttu-id="c2fd0-123">Por ejemplo, el siguiente código no escribe una codificación en la declaración XML que se encuentra en el archivo de salida `out.xml`.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-123">For example, the following code does not write an encoding in the XML declaration found in the output file `out.xml`.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
Dim tw As XmlTextWriter = New XmlTextWriter("out.xml", Nothing)  
doc.Load("text.xml")  
doc.Save(tw)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlTextWriter tw = new XmlTextWriter("out.xml", null);  
doc.Load("text.xml");  
doc.Save(tw);  
```  
  
 <span data-ttu-id="c2fd0-124">Para el método <xref:System.Xml.XmlDocument.Save%2A>, la declaración XML se escribe utilizando el método <xref:System.Xml.XmlWriter.WriteStartDocument%2A> en la clase <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-124">For the <xref:System.Xml.XmlDocument.Save%2A> method, the XML declaration is written out using the <xref:System.Xml.XmlWriter.WriteStartDocument%2A> method in the <xref:System.Xml.XmlWriter> class.</span></span> <span data-ttu-id="c2fd0-125">Por lo tanto, al sobrescribir el método <xref:System.Xml.XmlWriter.WriteStartDocument%2A>, cambia la forma de escribir el principio del documento.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-125">Therefore, overwriting the <xref:System.Xml.XmlWriter.WriteStartDocument%2A> method changes how the start of the document is written.</span></span>  
  
 <span data-ttu-id="c2fd0-126">Para los miembros <xref:System.Xml.XmlDeclaration> de <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlDeclaration.WriteTo%2A> y <xref:System.Xml.XmlNode.InnerXml%2A>, si no se establece la propiedad <xref:System.Xml.XmlDeclaration.Encoding%2A>, no se escribe la codificación. De lo contrario, la codificación escrita en la declaración XML es la misma que la que se encuentra en la propiedad <xref:System.Xml.XmlDeclaration.Encoding%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-126">For the <xref:System.Xml.XmlDeclaration> members of <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlDeclaration.WriteTo%2A>, and <xref:System.Xml.XmlNode.InnerXml%2A>, if the <xref:System.Xml.XmlDeclaration.Encoding%2A> property is not set, no encoding is written out. Otherwise, the encoding written out in the XML declaration is the same as the encoding found in the <xref:System.Xml.XmlDeclaration.Encoding%2A> property.</span></span>  
  
## <a name="writing-document-content-using-the-outerxml-property"></a><span data-ttu-id="c2fd0-127">Escribir el contenido de un documento con la propiedad OuterXml</span><span class="sxs-lookup"><span data-stu-id="c2fd0-127">Writing Document Content Using the OuterXml Property</span></span>  

 <span data-ttu-id="c2fd0-128">La propiedad <xref:System.Xml.XmlNode.OuterXml%2A> es una extensión de Microsoft de los estándares del Modelo de objetos de documento (DOM) XML del W3C (World Wide Web Consortium).</span><span class="sxs-lookup"><span data-stu-id="c2fd0-128">The <xref:System.Xml.XmlNode.OuterXml%2A> property is a Microsoft extension to the World Wide Web Consortium (W3C) XML Document Object Model (DOM) standards.</span></span> <span data-ttu-id="c2fd0-129">La propiedad <xref:System.Xml.XmlNode.OuterXml%2A> se utiliza para obtener el marcado de todo el documento XML o tan solo el de un nodo y sus nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-129">The <xref:System.Xml.XmlNode.OuterXml%2A> property is used to get the markup of the whole XML document, or just the markup of a single node and its child nodes.</span></span> <span data-ttu-id="c2fd0-130"><xref:System.Xml.XmlNode.OuterXml%2A>devuelve el marcado que representa el nodo en concreto y todos sus nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-130"><xref:System.Xml.XmlNode.OuterXml%2A> returns the markup representing the given node and all its child nodes.</span></span>  
  
 <span data-ttu-id="c2fd0-131">El siguiente ejemplo de código muestra cómo guardar un documento por completo como una cadena.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-131">The following code sample shows how to save a document in its entirety as a string.</span></span>  
  
```vb  
Dim mydoc As New XmlDocument()  
' Perform application needs here, like mydoc.Load("myfile");  
' Now save the entire document to a string variable called "xml".  
Dim xml As String = mydoc.OuterXml  
```  
  
```csharp  
XmlDocument mydoc = new XmlDocument();  
// Perform application needs here, like mydoc.Load("myfile");  
// Now save the entire document to a string variable called "xml".  
string xml = mydoc.OuterXml;  
```  
  
 <span data-ttu-id="c2fd0-132">El siguiente ejemplo de código muestra cómo guardar únicamente el elemento de documento.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-132">The following code sample shows how to save only the document element.</span></span>  
  
```vb  
' For the content of the Document Element only.  
Dim xml As String = mydoc.DocumentElement.OuterXml  
```  
  
```csharp  
// For the content of the Document Element only.  
string xml = mydoc.DocumentElement.OuterXml;  
```  
  
 <span data-ttu-id="c2fd0-133">Por el contrario, puede utilizar la propiedad <xref:System.Xml.XmlNode.InnerText%2A> si desea el contenido de los nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="c2fd0-133">In contrast, you can use the <xref:System.Xml.XmlNode.InnerText%2A> property if you want the content of child nodes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2fd0-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2fd0-134">See also</span></span>

- [<span data-ttu-id="c2fd0-135">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="c2fd0-135">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
