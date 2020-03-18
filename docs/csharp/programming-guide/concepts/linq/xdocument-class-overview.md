---
title: Información general de la clase XDocument (C#)
ms.date: 07/20/2015
ms.assetid: 63305603-ab54-49fc-84e4-f76eecc59549
ms.openlocfilehash: de49dc071d22dd77dddea29ca114663261e3edda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "69590843"
---
# <a name="xdocument-class-overview-c"></a><span data-ttu-id="91f5c-102">Información general de la clase XDocument (C#)</span><span class="sxs-lookup"><span data-stu-id="91f5c-102">XDocument Class Overview (C#)</span></span>
<span data-ttu-id="91f5c-103">En este tema se presenta la clase <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="91f5c-103">This topic introduces the <xref:System.Xml.Linq.XDocument> class.</span></span>  
  
## <a name="overview-of-the-xdocument-class"></a><span data-ttu-id="91f5c-104">Información general acerca de la clase XDocument</span><span class="sxs-lookup"><span data-stu-id="91f5c-104">Overview of the XDocument class</span></span>  
 <span data-ttu-id="91f5c-105">La clase <xref:System.Xml.Linq.XDocument> contiene la información necesaria para un documento XML válido.</span><span class="sxs-lookup"><span data-stu-id="91f5c-105">The <xref:System.Xml.Linq.XDocument> class contains the information necessary for a valid XML document.</span></span> <span data-ttu-id="91f5c-106">Incluye una declaración XML, instrucciones de procesamiento y comentarios.</span><span class="sxs-lookup"><span data-stu-id="91f5c-106">This includes an XML declaration, processing instructions, and comments.</span></span>  
  
 <span data-ttu-id="91f5c-107">Tenga en cuenta que solo debe crear objetos <xref:System.Xml.Linq.XDocument> si necesita la funcionalidad específica que proporciona la clase <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="91f5c-107">Note that you only have to create <xref:System.Xml.Linq.XDocument> objects if you require the specific functionality provided by the <xref:System.Xml.Linq.XDocument> class.</span></span> <span data-ttu-id="91f5c-108">En muchas circunstancias, puede trabajar directamente con <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="91f5c-108">In many circumstances, you can work directly with <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="91f5c-109">Trabajar directamente con <xref:System.Xml.Linq.XElement> constituye un modelo de programación más simple.</span><span class="sxs-lookup"><span data-stu-id="91f5c-109">Working directly with <xref:System.Xml.Linq.XElement> is a simpler programming model.</span></span>  
  
 <span data-ttu-id="91f5c-110"><xref:System.Xml.Linq.XDocument> se deriva de <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="91f5c-110"><xref:System.Xml.Linq.XDocument> derives from <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="91f5c-111">Por lo tanto, puede contener nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="91f5c-111">Therefore, it can contain child nodes.</span></span> <span data-ttu-id="91f5c-112">Sin embargo, los objetos <xref:System.Xml.Linq.XDocument> solo pueden tener un nodo <xref:System.Xml.Linq.XElement> secundario.</span><span class="sxs-lookup"><span data-stu-id="91f5c-112">However, <xref:System.Xml.Linq.XDocument> objects can have only one child <xref:System.Xml.Linq.XElement> node.</span></span> <span data-ttu-id="91f5c-113">Esto refleja el estándar XML: solo puede haber un elemento raíz en un documento XML.</span><span class="sxs-lookup"><span data-stu-id="91f5c-113">This reflects the XML standard that there can be only one root element in an XML document.</span></span>  
  
## <a name="components-of-xdocument"></a><span data-ttu-id="91f5c-114">Componentes de XDocument</span><span class="sxs-lookup"><span data-stu-id="91f5c-114">Components of XDocument</span></span>  
 <span data-ttu-id="91f5c-115">Un objeto <xref:System.Xml.Linq.XDocument> puede contener los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="91f5c-115">An <xref:System.Xml.Linq.XDocument> can contain the following elements:</span></span>  
  
- <span data-ttu-id="91f5c-116">Un objeto <xref:System.Xml.Linq.XDeclaration>.</span><span class="sxs-lookup"><span data-stu-id="91f5c-116">One <xref:System.Xml.Linq.XDeclaration> object.</span></span> <span data-ttu-id="91f5c-117"><xref:System.Xml.Linq.XDeclaration> permite especificar las partes pertinentes de una declaración XML: la versión XML, la codificación del documento y si el documento XML es independiente.</span><span class="sxs-lookup"><span data-stu-id="91f5c-117"><xref:System.Xml.Linq.XDeclaration> enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is stand-alone.</span></span>  
  
- <span data-ttu-id="91f5c-118">Un objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="91f5c-118">One <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="91f5c-119">Es el nodo raíz del documento XML.</span><span class="sxs-lookup"><span data-stu-id="91f5c-119">This is the root node of the XML document.</span></span>  
  
- <span data-ttu-id="91f5c-120">Cualquier número de objetos <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="91f5c-120">Any number of <xref:System.Xml.Linq.XProcessingInstruction> objects.</span></span> <span data-ttu-id="91f5c-121">Una instrucción de procesamiento comunica información a una aplicación que procesa el XML.</span><span class="sxs-lookup"><span data-stu-id="91f5c-121">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
- <span data-ttu-id="91f5c-122">Cualquier número de objetos <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="91f5c-122">Any number of <xref:System.Xml.Linq.XComment> objects.</span></span> <span data-ttu-id="91f5c-123">Los comentarios serán del mismo nivel que el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="91f5c-123">The comments will be siblings to the root element.</span></span> <span data-ttu-id="91f5c-124">El objeto <xref:System.Xml.Linq.XComment> no puede ser el primer argumento de la lista, ya que no es válido que el documento XML empiece con un comentario.</span><span class="sxs-lookup"><span data-stu-id="91f5c-124">The <xref:System.Xml.Linq.XComment> object cannot be the first argument in the list, because it is not valid for an XML document to start with a comment.</span></span>  
  
- <span data-ttu-id="91f5c-125">Un elemento <xref:System.Xml.Linq.XDocumentType> para el DTD.</span><span class="sxs-lookup"><span data-stu-id="91f5c-125">One <xref:System.Xml.Linq.XDocumentType> for the DTD.</span></span>  
  
 <span data-ttu-id="91f5c-126">Al serializar un objeto <xref:System.Xml.Linq.XDocument>, aunque `XDocument.Declaration` sea `null`, el resultado generará una declaración XML, siempre y cuando el redactor haya establecido `Writer.Settings.OmitXmlDeclaration` en `false` (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="91f5c-126">When you serialize an <xref:System.Xml.Linq.XDocument>, even if `XDocument.Declaration` is `null`, the output will have an XML declaration if the writer has `Writer.Settings.OmitXmlDeclaration` set to `false` (the default).</span></span>  
  
 <span data-ttu-id="91f5c-127">De manera predeterminada, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] establece la versión en "1.0" y la codificación en "utf-8".</span><span class="sxs-lookup"><span data-stu-id="91f5c-127">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sets the version to "1.0", and sets the encoding to "utf-8".</span></span>  
  
## <a name="using-xelement-without-xdocument"></a><span data-ttu-id="91f5c-128">Usar XElement sin XDocument</span><span class="sxs-lookup"><span data-stu-id="91f5c-128">Using XElement without XDocument</span></span>  
 <span data-ttu-id="91f5c-129">Tal como se indicó anteriormente, la clase <xref:System.Xml.Linq.XElement> es la clase principal de la interfaz de programación [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91f5c-129">As previously mentioned, the <xref:System.Xml.Linq.XElement> class is the main class in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface.</span></span> <span data-ttu-id="91f5c-130">En muchos casos, la aplicación no requerirá la creación de un documento.</span><span class="sxs-lookup"><span data-stu-id="91f5c-130">In many cases, your application will not require that you create a document.</span></span> <span data-ttu-id="91f5c-131">Mediante la clase <xref:System.Xml.Linq.XElement>, puede crear un árbol XML, agregarle otros árboles XML, modificar el árbol XML o guardarlo.</span><span class="sxs-lookup"><span data-stu-id="91f5c-131">By using the <xref:System.Xml.Linq.XElement> class, you can create an XML tree, add other XML trees to it, modify the XML tree, and save it.</span></span>  
  
## <a name="using-xdocument"></a><span data-ttu-id="91f5c-132">Usar XDocument</span><span class="sxs-lookup"><span data-stu-id="91f5c-132">Using XDocument</span></span>  
 <span data-ttu-id="91f5c-133">Para construir un objeto <xref:System.Xml.Linq.XDocument>, use la construcción funcional, al igual que cuando se construyen objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="91f5c-133">To construct an <xref:System.Xml.Linq.XDocument>, use functional construction, just like you do to construct <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="91f5c-134">El código siguiente crea un objeto <xref:System.Xml.Linq.XDocument> y sus objetos contenidos asociados.</span><span class="sxs-lookup"><span data-stu-id="91f5c-134">The following code creates an <xref:System.Xml.Linq.XDocument> object and its associated contained objects.</span></span>  
  
```csharp  
XDocument d = new XDocument(  
    new XComment("This is a comment."),  
    new XProcessingInstruction("xml-stylesheet",  
        "href='mystyle.css' title='Compact' type='text/css'"),  
    new XElement("Pubs",  
        new XElement("Book",  
            new XElement("Title", "Artifacts of Roman Civilization"),  
            new XElement("Author", "Moreno, Jordao")  
        ),  
        new XElement("Book",  
            new XElement("Title", "Midieval Tools and Implements"),  
            new XElement("Author", "Gazit, Inbar")  
        )  
    ),  
    new XComment("This is another comment.")  
);  
d.Declaration = new XDeclaration("1.0", "utf-8", "true");  
Console.WriteLine(d);  
  
d.Save("test.xml");  
```  
  
 <span data-ttu-id="91f5c-135">Al examinar el archivo test.xml, obtendrá el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="91f5c-135">When you examine the file test.xml, you get the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<!--This is a comment.-->  
<?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>  
<Pubs>  
  <Book>  
    <Title>Artifacts of Roman Civilization</Title>  
    <Author>Moreno, Jordao</Author>  
  </Book>  
  <Book>  
    <Title>Midieval Tools and Implements</Title>  
    <Author>Gazit, Inbar</Author>  
  </Book>  
</Pubs>  
<!--This is another comment.-->  
```  
  
## <a name="see-also"></a><span data-ttu-id="91f5c-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="91f5c-136">See also</span></span>

- [<span data-ttu-id="91f5c-137">Información general sobre la programación de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="91f5c-137">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
