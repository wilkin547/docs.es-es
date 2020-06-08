---
title: Creación de nuevos nodos en el DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 6c2b9789-b61a-49f9-b33f-db01a945edf2
ms.openlocfilehash: d99a3c68c7554ab266d71a4cbf2e676bc6db8cbc
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289582"
---
# <a name="create-new-nodes-in-the-dom"></a><span data-ttu-id="f47de-102">Creación de nuevos nodos en el DOM</span><span class="sxs-lookup"><span data-stu-id="f47de-102">Create New Nodes in the DOM</span></span>
<span data-ttu-id="f47de-103"><xref:System.Xml.XmlDocument> tiene un método de creación para todos los tipos de nodos.</span><span class="sxs-lookup"><span data-stu-id="f47de-103">The <xref:System.Xml.XmlDocument> has a create method for all of the node types.</span></span> <span data-ttu-id="f47de-104">Para crear el nodo, proporcione el método con un nombre cuando sea preciso, y el contenido y otros parámetros para aquellos nodos que tengan contenido (por ejemplo, los nodos de texto).</span><span class="sxs-lookup"><span data-stu-id="f47de-104">Supply the method with a name when required, and content or other parameters for those nodes that have content (for example, a text node), and the node is created.</span></span> <span data-ttu-id="f47de-105">Los siguientes métodos son los que necesitan que se proporcione un nombre y otros cuantos parámetros para crear un nodo apropiado.</span><span class="sxs-lookup"><span data-stu-id="f47de-105">The following methods are ones that need a name and a few other parameters filled to create an appropriate node.</span></span>  
  
- <xref:System.Xml.XmlDocument.CreateCDataSection%2A>  
  
- <xref:System.Xml.XmlDocument.CreateComment%2A>  
  
- <xref:System.Xml.XmlDocument.CreateDocumentFragment%2A>  
  
- <xref:System.Xml.XmlDocument.CreateDocumentType%2A>  
  
- <xref:System.Xml.XmlDocument.CreateElement%2A>  
  
- <xref:System.Xml.XmlDocument.CreateNode%2A>  
  
- <xref:System.Xml.XmlDocument.CreateProcessingInstruction%2A>  
  
- <xref:System.Xml.XmlDocument.CreateSignificantWhitespace%2A>  
  
- <xref:System.Xml.XmlDocument.CreateTextNode%2A>  
  
- <xref:System.Xml.XmlDocument.CreateWhitespace%2A>  
  
- <xref:System.Xml.XmlDocument.CreateXmlDeclaration%2A>  
  
 <span data-ttu-id="f47de-106">Otros tipos de nodos tienen más requisitos aparte de que se proporcionen datos a los parámetros.</span><span class="sxs-lookup"><span data-stu-id="f47de-106">Other node types have more requirements than just providing data to parameters.</span></span>  
  
 <span data-ttu-id="f47de-107">Para obtener más información sobre atributos, vea [Crear nuevos atributos para elementos en DOM](creating-new-attributes-for-elements-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="f47de-107">For information on attributes, see [Creating New Attributes for Elements in the DOM](creating-new-attributes-for-elements-in-the-dom.md).</span></span> <span data-ttu-id="f47de-108">Para obtener información sobre la validación de nombres de atributos y elementos, vea [Comprobación de nombres de atributos y elementos XML al crear nuevos nodos](xml-element-and-attribute-name-verification-when-creating-new-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="f47de-108">For information on element and attribute name validation, see [XML Element and Attribute Name Verification when Creating New Nodes](xml-element-and-attribute-name-verification-when-creating-new-nodes.md).</span></span> <span data-ttu-id="f47de-109">Para crear referencias de entidad, vea [Creación de nuevas referencias de entidad](creating-new-entity-references.md).</span><span class="sxs-lookup"><span data-stu-id="f47de-109">For creating entity references, see [Creating New Entity References](creating-new-entity-references.md).</span></span> <span data-ttu-id="f47de-110">Para obtener información sobre cómo los espacios de nombres afectan a la expansión de referencias de entidad, vea [Efecto del espacio de nombres en la expansión de referencias de entidad de nuevos nodos que contienen elementos y atributos](namespace-affect-on-entity-ref-expansion-for-new-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="f47de-110">For information on how namespaces affect the expansion of entity references, see [Namespace Affect on Entity Reference Expansion for New Nodes Containing Elements and Attributes](namespace-affect-on-entity-ref-expansion-for-new-nodes.md).</span></span>  
  
 <span data-ttu-id="f47de-111">Una vez creados los nuevos nodos, hay disponibles varios métodos para insertarlos en el árbol.</span><span class="sxs-lookup"><span data-stu-id="f47de-111">Once new nodes are created, there are several methods available to insert them into the tree.</span></span> <span data-ttu-id="f47de-112">En la tabla se enumeran los métodos con una descripción de dónde aparece el nuevo nodo en el Modelo de objetos de documento (DOM).</span><span class="sxs-lookup"><span data-stu-id="f47de-112">The table lists the methods with a description of where the new node appears in the XML Document Object Model (DOM).</span></span>  
  
|<span data-ttu-id="f47de-113">Método</span><span class="sxs-lookup"><span data-stu-id="f47de-113">Method</span></span>|<span data-ttu-id="f47de-114">Colocación del nodo</span><span class="sxs-lookup"><span data-stu-id="f47de-114">Node placement</span></span>|  
|------------|--------------------|  
|<xref:System.Xml.XmlNode.InsertBefore%2A>|<span data-ttu-id="f47de-115">Insertado antes del nodo de referencia.</span><span class="sxs-lookup"><span data-stu-id="f47de-115">Inserted before the reference node.</span></span> <span data-ttu-id="f47de-116">Por ejemplo, para insertar el nuevo nodo en la posición 5:</span><span class="sxs-lookup"><span data-stu-id="f47de-116">For example, to insert the new node in position 5:</span></span><br /><br /> `Dim refChild As XmlNode = node.ChildNodes(4) 'The reference is zero-based.node.InsertBefore(newChild, refChild);`<br /><br /> `XmlNode refChild = node.ChildNodes[4]; //The reference is zero-based. node.InsertBefore(newChild, refChild);`<br /><br /> <span data-ttu-id="f47de-117">Para obtener más información, vea el método <xref:System.Xml.XmlNode.InsertBefore%2A>.</span><span class="sxs-lookup"><span data-stu-id="f47de-117">For more information, see the <xref:System.Xml.XmlNode.InsertBefore%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.InsertAfter%2A>|<span data-ttu-id="f47de-118">Insertado después del nodo de referencia.</span><span class="sxs-lookup"><span data-stu-id="f47de-118">Inserted after the reference node.</span></span> <span data-ttu-id="f47de-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f47de-119">For example:</span></span><br /><br /> `node.InsertAfter(newChild, refChild)`<br /><br /> `node.InsertAfter(newChild, refChild);`<br /><br /> <span data-ttu-id="f47de-120">Para obtener más información, vea el método <xref:System.Xml.XmlNode.InsertAfter%2A>.</span><span class="sxs-lookup"><span data-stu-id="f47de-120">For more information, see the <xref:System.Xml.XmlNode.InsertAfter%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.AppendChild%2A>|<span data-ttu-id="f47de-121">Agrega el nodo al final de la lista de nodos secundarios del nodo especificado.</span><span class="sxs-lookup"><span data-stu-id="f47de-121">Adds the node to the end of the list of child nodes for the given node.</span></span> <span data-ttu-id="f47de-122">Si el nodo se agrega como un <xref:System.Xml.XmlDocumentFragment>, todo el contenido del fragmento del documento se mueve a la lista secundaria de este nodo.</span><span class="sxs-lookup"><span data-stu-id="f47de-122">If the node being added is an <xref:System.Xml.XmlDocumentFragment>, the entire contents of the document fragment are moved into the child list of this node.</span></span> <span data-ttu-id="f47de-123">Para obtener más información, vea el método <xref:System.Xml.XmlNode.AppendChild%2A>.</span><span class="sxs-lookup"><span data-stu-id="f47de-123">For more information, see the <xref:System.Xml.XmlNode.AppendChild%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.PrependChild%2A>|<span data-ttu-id="f47de-124">Agrega el nodo al principio de la lista de nodos secundarios del nodo especificado.</span><span class="sxs-lookup"><span data-stu-id="f47de-124">Adds the node to the beginning of the list of child nodes of the given node.</span></span> <span data-ttu-id="f47de-125">Si el nodo se agrega como un <xref:System.Xml.XmlDocumentFragment>, todo el contenido del fragmento del documento se mueve a la lista secundaria de este nodo.</span><span class="sxs-lookup"><span data-stu-id="f47de-125">If the node being added is an <xref:System.Xml.XmlDocumentFragment>, the entire contents of the document fragment are moved into the child list of this node.</span></span> <span data-ttu-id="f47de-126">Para obtener más información, vea el método <xref:System.Xml.XmlNode.PrependChild%2A>.</span><span class="sxs-lookup"><span data-stu-id="f47de-126">For more information, see the <xref:System.Xml.XmlNode.PrependChild%2A> method.</span></span>|  
|<xref:System.Xml.XmlAttributeCollection.Append%2A>|<span data-ttu-id="f47de-127">Agrega un nodo <xref:System.Xml.XmlAttribute> al final de la colección de atributos asociada a un elemento.</span><span class="sxs-lookup"><span data-stu-id="f47de-127">Appends an <xref:System.Xml.XmlAttribute> node to the end of the attribute collection associated with an element.</span></span> <span data-ttu-id="f47de-128">Para obtener más información, vea el método <xref:System.Xml.XmlAttributeCollection.Append%2A>.</span><span class="sxs-lookup"><span data-stu-id="f47de-128">For more information, see the <xref:System.Xml.XmlAttributeCollection.Append%2A> method.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f47de-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f47de-129">See also</span></span>

- [<span data-ttu-id="f47de-130">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="f47de-130">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
