---
title: "Información general de las clases LINQ to XML (C#)"
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
ms.assetid: bf666100-5392-4968-97f4-f6b9d3287d7b
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: de9664f56a0ab075d2c74b45d0eebab541213d06
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="linq-to-xml-classes-overview-c"></a><span data-ttu-id="149e9-102">Información general de las clases LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="149e9-102">LINQ to XML Classes Overview (C#)</span></span>
<span data-ttu-id="149e9-103">En este tema se proporciona una lista de las clases de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en el espacio de nombres <xref:System.Xml.Linq> y proporciona una breve descripción de cada una.</span><span class="sxs-lookup"><span data-stu-id="149e9-103">This topic provides a list of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] classes in the <xref:System.Xml.Linq> namespace, and a short description of each.</span></span>  
  
## <a name="linq-to-xml-classes"></a><span data-ttu-id="149e9-104">Clases de LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="149e9-104">LINQ to XML Classes</span></span>  
  
### <a name="xattribute-class"></a><span data-ttu-id="149e9-105">Clase XAttribute</span><span class="sxs-lookup"><span data-stu-id="149e9-105">XAttribute Class</span></span>  
 <span data-ttu-id="149e9-106"><xref:System.Xml.Linq.XAttribute> representa un atributo XML.</span><span class="sxs-lookup"><span data-stu-id="149e9-106"><xref:System.Xml.Linq.XAttribute> represents an XML attribute.</span></span> <span data-ttu-id="149e9-107">Para obtener información detallada y ejemplos, vea [Información general acerca de la clase XAttribute](../../../../csharp/programming-guide/concepts/linq/xattribute-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="149e9-107">For detailed information and examples, see [XAttribute Class Overview (C#)](../../../../csharp/programming-guide/concepts/linq/xattribute-class-overview.md).</span></span>  
  
### <a name="xcdata-class"></a><span data-ttu-id="149e9-108">Clase XCData</span><span class="sxs-lookup"><span data-stu-id="149e9-108">XCData Class</span></span>  
 <span data-ttu-id="149e9-109"><xref:System.Xml.Linq.XCData> representa un nodo de texto CDATA.</span><span class="sxs-lookup"><span data-stu-id="149e9-109"><xref:System.Xml.Linq.XCData> represents a CDATA text node.</span></span>  
  
### <a name="xcomment-class"></a><span data-ttu-id="149e9-110">Clase XComment</span><span class="sxs-lookup"><span data-stu-id="149e9-110">XComment Class</span></span>  
 <span data-ttu-id="149e9-111"><xref:System.Xml.Linq.XComment> representa un comentario XML.</span><span class="sxs-lookup"><span data-stu-id="149e9-111"><xref:System.Xml.Linq.XComment> represents an XML comment.</span></span>  
  
### <a name="xcontainer-class"></a><span data-ttu-id="149e9-112">Clase XContainer</span><span class="sxs-lookup"><span data-stu-id="149e9-112">XContainer Class</span></span>  
 <span data-ttu-id="149e9-113"><xref:System.Xml.Linq.XContainer> es una clase base abstracta para todos los nodos que pueden tener nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="149e9-113"><xref:System.Xml.Linq.XContainer> is an abstract base class for all nodes that can have child nodes.</span></span> <span data-ttu-id="149e9-114">Las siguientes clases se derivan de la clase <xref:System.Xml.Linq.XContainer>:</span><span class="sxs-lookup"><span data-stu-id="149e9-114">The following classes derive from the <xref:System.Xml.Linq.XContainer> class:</span></span>  
  
-   <xref:System.Xml.Linq.XElement>  
  
-   <xref:System.Xml.Linq.XDocument>  
  
### <a name="xdeclaration-class"></a><span data-ttu-id="149e9-115">Clase XDeclaration</span><span class="sxs-lookup"><span data-stu-id="149e9-115">XDeclaration Class</span></span>  
 <span data-ttu-id="149e9-116"><xref:System.Xml.Linq.XDeclaration> representa una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="149e9-116"><xref:System.Xml.Linq.XDeclaration> represents an XML declaration.</span></span> <span data-ttu-id="149e9-117">Una declaración XML se utiliza para declarar la versión de XML y la codificación de un documento.</span><span class="sxs-lookup"><span data-stu-id="149e9-117">An XML declaration is used to declare the XML version and the encoding of a document.</span></span> <span data-ttu-id="149e9-118">Asimismo, una declaración XML especifica si el documento XML es independiente.</span><span class="sxs-lookup"><span data-stu-id="149e9-118">In addition, an XML declaration specifies whether the XML document is stand-alone.</span></span> <span data-ttu-id="149e9-119">Si un documento es independiente, no hay declaraciones de marcado externas, ya sea en un DTD externo o en una entidad de parámetro externa a la que se hace referencia desde el subconjunto interno.</span><span class="sxs-lookup"><span data-stu-id="149e9-119">If a document is stand-alone, there are no external markup declarations, either in an external DTD, or in an external parameter entity referenced from the internal subset.</span></span>  
  
### <a name="xdocument-class"></a><span data-ttu-id="149e9-120">Clase XDocument</span><span class="sxs-lookup"><span data-stu-id="149e9-120">XDocument Class</span></span>  
 <span data-ttu-id="149e9-121"><xref:System.Xml.Linq.XDocument> representa un documento XML.</span><span class="sxs-lookup"><span data-stu-id="149e9-121"><xref:System.Xml.Linq.XDocument> represents an XML document.</span></span> <span data-ttu-id="149e9-122">Para obtener información detallada y ejemplos, vea [Información general acerca de la clase XDocument](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="149e9-122">For detailed information and examples, see [XDocument Class Overview (C#)](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).</span></span>  
  
### <a name="xdocumenttype-class"></a><span data-ttu-id="149e9-123">Clase XDocumentType</span><span class="sxs-lookup"><span data-stu-id="149e9-123">XDocumentType Class</span></span>  
 <span data-ttu-id="149e9-124"><xref:System.Xml.Linq.XDocumentType> representa una definición de tipo del documento (DTD) XML.</span><span class="sxs-lookup"><span data-stu-id="149e9-124"><xref:System.Xml.Linq.XDocumentType> represents an XML Document Type Definition (DTD).</span></span>  
  
### <a name="xelement-class"></a><span data-ttu-id="149e9-125">Clase XElement</span><span class="sxs-lookup"><span data-stu-id="149e9-125">XElement Class</span></span>  
 <span data-ttu-id="149e9-126"><xref:System.Xml.Linq.XElement> representa un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="149e9-126"><xref:System.Xml.Linq.XElement> represents an XML element.</span></span> <span data-ttu-id="149e9-127">Para obtener información detallada y ejemplos, vea [Información general acerca de la clase XElement](../../../../csharp/programming-guide/concepts/linq/xelement-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="149e9-127">For detailed information and examples, see [XElement Class Overview (C#)](../../../../csharp/programming-guide/concepts/linq/xelement-class-overview.md).</span></span>  
  
### <a name="xname-class"></a><span data-ttu-id="149e9-128">Clase XName</span><span class="sxs-lookup"><span data-stu-id="149e9-128">XName Class</span></span>  
 <span data-ttu-id="149e9-129"><xref:System.Xml.Linq.XName> representa nombres de elementos (<xref:System.Xml.Linq.XElement>) y atributos (<xref:System.Xml.Linq.XAttribute>).</span><span class="sxs-lookup"><span data-stu-id="149e9-129"><xref:System.Xml.Linq.XName> represents names of elements (<xref:System.Xml.Linq.XElement>) and attributes (<xref:System.Xml.Linq.XAttribute>).</span></span> <span data-ttu-id="149e9-130">Para obtener información detallada y ejemplos, vea [Información general acerca de la clase XDocument](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="149e9-130">For detailed information and examples, see [XDocument Class Overview (C#)](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="149e9-131"> se ha diseñado para hacer que los nombres XML sean tan sencillos como sea posible.</span><span class="sxs-lookup"><span data-stu-id="149e9-131"> is designed to make XML names as straightforward as possible.</span></span> <span data-ttu-id="149e9-132">Debido a su complejidad, los nombres XML a menudo se consideran un tema avanzado en XML.</span><span class="sxs-lookup"><span data-stu-id="149e9-132">Due to their complexity, XML names are often considered to be an advanced topic in XML.</span></span> <span data-ttu-id="149e9-133">Puede argumentarse que la complejidad no proviene de los espacios de nombres, que los desarrolladores usan regularmente en la programación, sino de los prefijos de los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="149e9-133">Arguably, this complexity comes not from namespaces, which developers use regularly in programming, but from namespace prefixes.</span></span> <span data-ttu-id="149e9-134">Los prefijos de los espacios de nombres pueden ser útiles para reducir las pulsaciones de teclas necesarias cuando se especifica código XML o hacer que el código XML sea más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="149e9-134">Namespace prefixes can be useful to reduce the keystrokes required when you input XML, or to make XML easier to read.</span></span> <span data-ttu-id="149e9-135">No obstante, a menudo los prefijos son un acceso directo al espacio de nombres XML completo y no son necesarios en la mayoría de los casos.</span><span class="sxs-lookup"><span data-stu-id="149e9-135">However, prefixes are often just a shortcut for using the full XML namespace, and are not required in most cases.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="149e9-136"> simplifica los nombres XML resolviendo todos los prefijos a su espacio de nombres XML correspondiente.</span><span class="sxs-lookup"><span data-stu-id="149e9-136"> simplifies XML names by resolving all prefixes to their corresponding XML namespace.</span></span> <span data-ttu-id="149e9-137">Los prefijos están disponibles, si son necesarios, a través del método <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="149e9-137">Prefixes are available, if they are required, through the <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A> method.</span></span>  
  
 <span data-ttu-id="149e9-138">Si es necesario es posible controlar los prefijos de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="149e9-138">It is possible, if necessary, to control namespace prefixes.</span></span> <span data-ttu-id="149e9-139">En algunas circunstancias, si trabaja con otros sistemas XML, como XSLT o XAML, debe controlar los prefijos de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="149e9-139">In some circumstances, if you are working with other XML systems, such as XSLT or XAML, you need to control namespace prefixes.</span></span> <span data-ttu-id="149e9-140">Por ejemplo, si tiene una expresión XPath que utiliza los prefijos del espacio de nombres que está incrustado en una hoja de estilos XSLT, deberá asegurarse de que el documento XML esté serializado con prefijos de espacio de nombres que coinciden con los que se utilizan en la expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="149e9-140">For example, if you have an XPath expression that uses namespace prefixes and is embedded in an XSLT stylesheet, you must make sure that your XML document is serialized with namespace prefixes that match those used in the XPath expression.</span></span>  
  
### <a name="xnamespace-class"></a><span data-ttu-id="149e9-141">Clase XNamespace</span><span class="sxs-lookup"><span data-stu-id="149e9-141">XNamespace Class</span></span>  
 <span data-ttu-id="149e9-142"><xref:System.Xml.Linq.XNamespace> representa un espacio de nombres para un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="149e9-142"><xref:System.Xml.Linq.XNamespace> represents a namespace for an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="149e9-143">Los espacios de nombres son un componente de un <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="149e9-143">Namespaces are a component of an <xref:System.Xml.Linq.XName>.</span></span>  
  
### <a name="xnode-class"></a><span data-ttu-id="149e9-144">Clase XNode</span><span class="sxs-lookup"><span data-stu-id="149e9-144">XNode Class</span></span>  
 <span data-ttu-id="149e9-145"><xref:System.Xml.Linq.XNode> es una clase abstracta que representa los nodos de un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="149e9-145"><xref:System.Xml.Linq.XNode> is an abstract class that represents the nodes of an XML tree.</span></span> <span data-ttu-id="149e9-146">Las siguientes clases se derivan de la clase <xref:System.Xml.Linq.XNode>:</span><span class="sxs-lookup"><span data-stu-id="149e9-146">The following classes derive from the <xref:System.Xml.Linq.XNode> class:</span></span>  
  
-   <xref:System.Xml.Linq.XText>  
  
-   <xref:System.Xml.Linq.XContainer>  
  
-   <xref:System.Xml.Linq.XComment>  
  
-   <xref:System.Xml.Linq.XProcessingInstruction>  
  
-   <xref:System.Xml.Linq.XDocumentType>  
  
### <a name="xnodedocumentordercomparer-class"></a><span data-ttu-id="149e9-147">Clase XNodeDocumentOrderComparer</span><span class="sxs-lookup"><span data-stu-id="149e9-147">XNodeDocumentOrderComparer Class</span></span>  
 <span data-ttu-id="149e9-148"><xref:System.Xml.Linq.XNodeDocumentOrderComparer> proporciona la funcionalidad para comparar el orden de documentos de los nodos.</span><span class="sxs-lookup"><span data-stu-id="149e9-148"><xref:System.Xml.Linq.XNodeDocumentOrderComparer> provides functionality to compare nodes for their document order.</span></span>  
  
### <a name="xnodeequalitycomparer-class"></a><span data-ttu-id="149e9-149">Clase XNodeEqualityComparer</span><span class="sxs-lookup"><span data-stu-id="149e9-149">XNodeEqualityComparer Class</span></span>  
 <span data-ttu-id="149e9-150"><xref:System.Xml.Linq.XNodeEqualityComparer> proporciona la funcionalidad para comparar la igualdad del valor de los nodos.</span><span class="sxs-lookup"><span data-stu-id="149e9-150"><xref:System.Xml.Linq.XNodeEqualityComparer> provides functionality to compare nodes for value equality.</span></span>  
  
### <a name="xobject-class"></a><span data-ttu-id="149e9-151">Clase XObject</span><span class="sxs-lookup"><span data-stu-id="149e9-151">XObject Class</span></span>  
 <span data-ttu-id="149e9-152"><xref:System.Xml.Linq.XObject> es una clase base abstracta de <xref:System.Xml.Linq.XNode> y <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="149e9-152"><xref:System.Xml.Linq.XObject> is an abstract base class of <xref:System.Xml.Linq.XNode> and <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="149e9-153">Proporciona funcionalidad de evento y anotación.</span><span class="sxs-lookup"><span data-stu-id="149e9-153">It provides annotation and event functionality.</span></span>  
  
### <a name="xobjectchange-class"></a><span data-ttu-id="149e9-154">Clase XObjectChange</span><span class="sxs-lookup"><span data-stu-id="149e9-154">XObjectChange Class</span></span>  
 <span data-ttu-id="149e9-155"><xref:System.Xml.Linq.XObjectChange> especifica el tipo de evento cuando se produce para un <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="149e9-155"><xref:System.Xml.Linq.XObjectChange> specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>  
  
### <a name="xobjectchangeeventargs-class"></a><span data-ttu-id="149e9-156">Clase XObjectChangeEventArgs</span><span class="sxs-lookup"><span data-stu-id="149e9-156">XObjectChangeEventArgs Class</span></span>  
 <span data-ttu-id="149e9-157"><xref:System.Xml.Linq.XObjectChangeEventArgs> proporciona datos para los eventos <xref:System.Xml.Linq.XObject.Changing> y <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="149e9-157"><xref:System.Xml.Linq.XObjectChangeEventArgs> provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>  
  
### <a name="xprocessinginstruction-class"></a><span data-ttu-id="149e9-158">Clase XProcessingInstruction</span><span class="sxs-lookup"><span data-stu-id="149e9-158">XProcessingInstruction Class</span></span>  
 <span data-ttu-id="149e9-159"><xref:System.Xml.Linq.XProcessingInstruction> representa una instrucción de procesamiento de XML.</span><span class="sxs-lookup"><span data-stu-id="149e9-159"><xref:System.Xml.Linq.XProcessingInstruction> represents an XML processing instruction.</span></span> <span data-ttu-id="149e9-160">Una instrucción de procesamiento comunica información a una aplicación que procesa el XML.</span><span class="sxs-lookup"><span data-stu-id="149e9-160">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
### <a name="xtext-class"></a><span data-ttu-id="149e9-161">Clase XText</span><span class="sxs-lookup"><span data-stu-id="149e9-161">XText Class</span></span>  
 <span data-ttu-id="149e9-162"><xref:System.Xml.Linq.XText> representa un nodo de texto.</span><span class="sxs-lookup"><span data-stu-id="149e9-162"><xref:System.Xml.Linq.XText> represents a text node.</span></span> <span data-ttu-id="149e9-163">En la mayoría de casos no tiene que usar esta clase.</span><span class="sxs-lookup"><span data-stu-id="149e9-163">In most cases, you do not have to use this class.</span></span> <span data-ttu-id="149e9-164">Esta clase se utiliza principalmente para el contenido mixto.</span><span class="sxs-lookup"><span data-stu-id="149e9-164">This class is primarily used for mixed content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="149e9-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="149e9-165">See Also</span></span>  
 [<span data-ttu-id="149e9-166">Información general sobre la programación de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="149e9-166">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)

