---
title: Información general de la clase XDocument (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 45cb7e71-196a-47da-bfe9-7a5589db1eed
ms.openlocfilehash: f9a531b9e90a8d6511dd0a2c6fc3131c9bfe1e89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907821"
---
# <a name="xdocument-class-overview-visual-basic"></a><span data-ttu-id="ff942-102">Información general de la clase XDocument (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff942-102">XDocument Class Overview (Visual Basic)</span></span>
<span data-ttu-id="ff942-103">En este tema se presenta la clase <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="ff942-103">This topic introduces the <xref:System.Xml.Linq.XDocument> class.</span></span>  
  
## <a name="overview-of-the-xdocument-class"></a><span data-ttu-id="ff942-104">Información general acerca de la clase XDocument</span><span class="sxs-lookup"><span data-stu-id="ff942-104">Overview of the XDocument class</span></span>  
 <span data-ttu-id="ff942-105">La clase <xref:System.Xml.Linq.XDocument> contiene la información necesaria para un documento XML válido.</span><span class="sxs-lookup"><span data-stu-id="ff942-105">The <xref:System.Xml.Linq.XDocument> class contains the information necessary for a valid XML document.</span></span> <span data-ttu-id="ff942-106">Incluye una declaración XML, instrucciones de procesamiento y comentarios.</span><span class="sxs-lookup"><span data-stu-id="ff942-106">This includes an XML declaration, processing instructions, and comments.</span></span>  
  
 <span data-ttu-id="ff942-107">Tenga en cuenta que solo debe crear objetos <xref:System.Xml.Linq.XDocument> si necesita la funcionalidad específica que proporciona la clase <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="ff942-107">Note that you only have to create <xref:System.Xml.Linq.XDocument> objects if you require the specific functionality provided by the <xref:System.Xml.Linq.XDocument> class.</span></span> <span data-ttu-id="ff942-108">En muchas circunstancias, puede trabajar directamente con <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ff942-108">In many circumstances, you can work directly with <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="ff942-109">Trabajar directamente con <xref:System.Xml.Linq.XElement> constituye un modelo de programación más simple.</span><span class="sxs-lookup"><span data-stu-id="ff942-109">Working directly with <xref:System.Xml.Linq.XElement> is a simpler programming model.</span></span>  
  
 <span data-ttu-id="ff942-110"><xref:System.Xml.Linq.XDocument> se deriva de <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="ff942-110"><xref:System.Xml.Linq.XDocument> derives from <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="ff942-111">Por lo tanto, puede contener nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="ff942-111">Therefore, it can contain child nodes.</span></span> <span data-ttu-id="ff942-112">Sin embargo, los objetos <xref:System.Xml.Linq.XDocument> solo pueden tener un nodo <xref:System.Xml.Linq.XElement> secundario.</span><span class="sxs-lookup"><span data-stu-id="ff942-112">However, <xref:System.Xml.Linq.XDocument> objects can have only one child <xref:System.Xml.Linq.XElement> node.</span></span> <span data-ttu-id="ff942-113">Esto refleja el estándar XML: solo puede haber un elemento raíz en un documento XML.</span><span class="sxs-lookup"><span data-stu-id="ff942-113">This reflects the XML standard that there can be only one root element in an XML document.</span></span>  
  
## <a name="components-of-xdocument"></a><span data-ttu-id="ff942-114">Componentes de XDocument</span><span class="sxs-lookup"><span data-stu-id="ff942-114">Components of XDocument</span></span>  
 <span data-ttu-id="ff942-115">Un objeto <xref:System.Xml.Linq.XDocument> puede contener los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="ff942-115">An <xref:System.Xml.Linq.XDocument> can contain the following elements:</span></span>  
  
-   <span data-ttu-id="ff942-116">Un objeto <xref:System.Xml.Linq.XDeclaration>.</span><span class="sxs-lookup"><span data-stu-id="ff942-116">One <xref:System.Xml.Linq.XDeclaration> object.</span></span> <span data-ttu-id="ff942-117"><xref:System.Xml.Linq.XDeclaration> permite especificar las partes pertinentes de una declaración XML: la versión XML, la codificación del documento y si el documento XML es independiente.</span><span class="sxs-lookup"><span data-stu-id="ff942-117"><xref:System.Xml.Linq.XDeclaration> enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is stand-alone.</span></span>  
  
-   <span data-ttu-id="ff942-118">Un objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ff942-118">One <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="ff942-119">Es el nodo raíz del documento XML.</span><span class="sxs-lookup"><span data-stu-id="ff942-119">This is the root node of the XML document.</span></span>  
  
-   <span data-ttu-id="ff942-120">Cualquier número de objetos <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="ff942-120">Any number of <xref:System.Xml.Linq.XProcessingInstruction> objects.</span></span> <span data-ttu-id="ff942-121">Una instrucción de procesamiento comunica información a una aplicación que procesa el XML.</span><span class="sxs-lookup"><span data-stu-id="ff942-121">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
-   <span data-ttu-id="ff942-122">Cualquier número de objetos <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="ff942-122">Any number of <xref:System.Xml.Linq.XComment> objects.</span></span> <span data-ttu-id="ff942-123">Los comentarios serán del mismo nivel que el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="ff942-123">The comments will be siblings to the root element.</span></span> <span data-ttu-id="ff942-124">El objeto <xref:System.Xml.Linq.XComment> no puede ser el primer argumento de la lista, ya que no es válido que el documento XML empiece con un comentario.</span><span class="sxs-lookup"><span data-stu-id="ff942-124">The <xref:System.Xml.Linq.XComment> object cannot be the first argument in the list, because it is not valid for an XML document to start with a comment.</span></span>  
  
-   <span data-ttu-id="ff942-125">Un elemento <xref:System.Xml.Linq.XDocumentType> para el DTD.</span><span class="sxs-lookup"><span data-stu-id="ff942-125">One <xref:System.Xml.Linq.XDocumentType> for the DTD.</span></span>  
  
 <span data-ttu-id="ff942-126">Al serializar un objeto <xref:System.Xml.Linq.XDocument>, aunque `XDocument.Declaration` sea `null`, el resultado generará una declaración XML, siempre y cuando el redactor haya establecido `Writer.Settings.OmitXmlDeclaration` en `false` (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="ff942-126">When you serialize an <xref:System.Xml.Linq.XDocument>, even if `XDocument.Declaration` is `null`, the output will have an XML declaration if the writer has `Writer.Settings.OmitXmlDeclaration` set to `false` (the default).</span></span>  
  
 <span data-ttu-id="ff942-127">De manera predeterminada, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] establece la versión en "1.0" y la codificación en "utf-8".</span><span class="sxs-lookup"><span data-stu-id="ff942-127">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sets the version to "1.0", and sets the encoding to "utf-8".</span></span>  
  
## <a name="using-xelement-without-xdocument"></a><span data-ttu-id="ff942-128">Usar XElement sin XDocument</span><span class="sxs-lookup"><span data-stu-id="ff942-128">Using XElement without XDocument</span></span>  
 <span data-ttu-id="ff942-129">Tal como se indicó anteriormente, la clase <xref:System.Xml.Linq.XElement> es la clase principal de la interfaz de programación [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff942-129">As previously mentioned, the <xref:System.Xml.Linq.XElement> class is the main class in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface.</span></span> <span data-ttu-id="ff942-130">En muchos casos, la aplicación no requerirá la creación de un documento.</span><span class="sxs-lookup"><span data-stu-id="ff942-130">In many cases, your application will not require that you create a document.</span></span> <span data-ttu-id="ff942-131">Mediante la clase <xref:System.Xml.Linq.XElement>, puede crear un árbol XML, agregarle otros árboles XML, modificar el árbol XML o guardarlo.</span><span class="sxs-lookup"><span data-stu-id="ff942-131">By using the <xref:System.Xml.Linq.XElement> class, you can create an XML tree, add other XML trees to it, modify the XML tree, and save it.</span></span>  
  
## <a name="using-xdocument"></a><span data-ttu-id="ff942-132">Usar XDocument</span><span class="sxs-lookup"><span data-stu-id="ff942-132">Using XDocument</span></span>  
 <span data-ttu-id="ff942-133">Para construir un objeto <xref:System.Xml.Linq.XDocument>, use la construcción funcional, al igual que cuando se construyen objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ff942-133">To construct an <xref:System.Xml.Linq.XDocument>, use functional construction, just like you do to construct <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="ff942-134">El código siguiente crea un objeto <xref:System.Xml.Linq.XDocument> y sus objetos contenidos asociados.</span><span class="sxs-lookup"><span data-stu-id="ff942-134">The following code creates an <xref:System.Xml.Linq.XDocument> object and its associated contained objects.</span></span>  
  
```vb  
Dim doc As XDocument = <?xml version="1.0" encoding="utf-8"?>  
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
doc.Save("test.xml")  
```  
  
 <span data-ttu-id="ff942-135">Al examinar el archivo test.xml, obtendrá el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="ff942-135">When you examine the file test.xml, you get the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ff942-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff942-136">See also</span></span>

- [<span data-ttu-id="ff942-137">LINQ to XML de información general de programación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff942-137">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
